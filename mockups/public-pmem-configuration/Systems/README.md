 # Configuring Persistent Memory

This mockup shows how to report and configure Persistent Memory DIMMs (PMEM) that support being configured as Volatile, Persistent or both, using POST and DELETE methods and the MemoryDomains, MemoryChunks and their associated collections.  It also assumes that the POST/DELETE methods will only take affect after a reboot, so the requests are tracked via Tasks.

This mockup does not include PATCH or reporting MemoryDomains or MemoryChunks for volatile memory, only persistent.  It does include reporting Regions for Volatile memory.

This mockup assumes that any capacity on a PMEM device not configured as Persistent will be allocated as volatile. An alternative mockup could assume any compacity on a PMEM device not configured as Persistent will be left unconfigured, thus no Volatile Regions created in response to a POST to create a persistent MemoryChunk that does not consume all of the PMEM device capacity.

To create a MemoryChunk and Regions required, POST a MemoryChunk to the MemoryChunkCollection in a specific MemoryDomain. In the POST, one of the InterleaveableSets in the MemoryDomain must be included as the InterleaveSets in the POST.

To delete a MemoryChunk, DELETE the MemoryChunk from the MemoryChunkCollection. Deleting a MemoryChunk will result in the corresponding Regions in the Memory instances being removed.

### MemoryChunk POST properties
- `AddressRangeType`: required
- `MemoryChunkSizeMiB`: optional, default value is 0. Maximum is the sum total of the CapacityMiB of each Memory in the InterleaveSets.
- `IsMirrorEnabled`: optional, default value is false
- `IsSpare`: optional, default is false
- `InterleaveSets`: required. Must match one of the `InterleavableMemorySets` in the corresponding MemoryDomain.

## Configuration Tasks
Since the POST and DELETE may not take affect until after a reboot, this mockup shows use of a Task for each request.  This mockup assumes all the Tasks will be processed, in order, after reboot and the Task status will be updated. PATCH to the MemoryChunk are not part of this mockup, so changes to the configuration must DELETE the MemoryChunk and re-create it.

## Configuration Sequencing
In this mockup, the intent of configuration will only be inferred from the sequence in which the requests are made. As such, any DELETE requests must precede any POST requests relating to MemoryDomains on the same socket. A DELETE request and a POST request may be done in the same reboot as long as they follow this rule.

### Example 1 for Sequencing

Example configuration is 2 PMEM devices, A1 and A2, of 16GiB each on a single socket on the same memory controller with 2 MemoryChunks, MC1 and MC2, configured for 100% persistent memory non-interleaved.

**Goal**: Reconfigure these 2 PMEM devices to be 100% persistent memory interleaved.

**Solution**: The user would first issue a DELETE request on MC1 and a separate DELETE request on MC2. This would create 2 New tasks in the task queue. The user would then issue a POST request on that MemoryDomain including DIMMs A1 and A2 in the corresponding InterleaveSets with a MemoryChunkSizeMiB of 32GiB. This would result in 3 New tasks in the task queue to be consumed on reboot. See details steps below:

1. Delete MC1
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks/MC1`
1. Delete MC2
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks/MC2`
1. Create new configuration: All persistent
   1. Operation: POST
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks`
   1. Body:
   ```json
   {
       "AddressRangeType": "PMEM",
       "MemoryChunkSizeMiB": 32768,
       "InterleaveSets": [
          {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/A1/"
            }
           },
           {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/A2/"
               }
           }
       ]
   }
   ```
1. Reboot system to apply


### Example 2 for Sequencing
Example configuration is 2 PMEM devices, A1 and A2, of 16GiB each on a single socket on the same memory controller with 2 MemoryChunks, MC1 and MC2, configured for 100% persistent memory non-interleaved. Also, 2 PMEM devices, B1 and B2, of 16GiB each on a single socket (separate than A1 and A2) on the same memory controller with 2 MemoryChunks, MC3 and MC4, configured for 100% persistent memory non-interleaved.

**Goal**: Reconfigure these 4 PMEM devices to be 50% persistent memory non-interleaved.

**Solution**: The user would first issue separate DELETE requests on MC1, MC2, MC3 and MC4. This would create 4 New tasks in the task queue. The user would then issue a POST request on the MemoryDomain corresponding to A1 with A1 in the corresponding InterleaveSets a MemoryChunkSizeMiB of 16GiB. The user would repeat this POST request on the MemoryDomains corresponding to A2, B1 and B2 with each of those respective DIMMs in their own InterleaveSets. This would result in 8 New tasks in the task queue that would be consumed on reboot. See detailed steps below:

1. Delete MC1
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks/MC1`
1. Delete MC2
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks/MC2`
1. Delete MC3
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC2MemoryDomain/MemoryChunks/MC3`
1. Delete MC4
   1. Operation: DELETE
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC2MemoryDomain/MemoryChunks/MC4`
1. Create new configuration using MemoryChunkSizePercentage for A1.
   1. Operation: POST
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks`
   1. Body:
   ```json
   {
       "AddressRangeType": "PMEM",
       "MemoryChunkSizeMiB": 16384,
       "InterleaveSets": [
            {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/A1/"
               }
           }
       ]
   }
   ```
1. Create new configuration using MemoryChunkSizePercentage for A2.
   1. Operation: POST
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC1MemoryDomain/MemoryChunks`
   1. Body:
   ```json
   {
       "AddressRangeType": "PMEM",
       "MemoryChunkSizeMiB": 16384,
       "InterleaveSets": [
            {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/A2/"
               }
           }
       ]
   }
   ```
1. Create new configuration using MemoryChunkSizePercentage for B1.
   1. Operation: POST
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC2MemoryDomain/MemoryChunks`
   1. Body:
   ```json
   {
       "AddressRangeType": "PMEM",
       "MemoryChunkSizeMiB": 16384,
       "InterleaveSets": [
            {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/B1/"
               }
           }
       ]
   }
   ```
1. Create new configuration using MemoryChunkSizePercentage for B2.
   1. Operation: POST
   1. Path: `/redfish/v1/Systems/1/MemoryDomains/PROC2MemoryDomain/MemoryChunks`
   1. Body:
   ```json
   {
       "AddressRangeType": "PMEM",
       "MemoryChunkSizeMiB": 16384,
       "InterleaveSets": [
            {
               "Memory": {
                   "@odata.id": "/redfish/v1/Systems/1/Memory/B2/"
               }
           }
       ]
   }
   ```
1. Reboot system to apply changed staged in iLO.

**Alternate Solution**: The user would first issue a DELETE request on MC1 (MemoryChunk corresponding to A1). Then the user would then issue a POST request on the MemoryDomain corresponding to A1 with A1 in the corresponding InterleaveSets and a MemoryChunkSizeMiB of 16GiB. The user would repeat this process for MC2, MC3 and MC4.  This would result in 8 New tasks in the task queue that would be consumed on reboot.

## Examples in this Repository

Example configuration is 2 PMEM devices of 16GiB each on a single socket on the same memory controller.

### InitialBoot
InitialBoot shows the Memory and MemoryDomain mock-up before the POST described below.  Initial configuration for PMEM devices will be all volatile.   This mockup does not include MemoryDomains or MemoryChunks for normal volatile DIMMs and will only show a MemoryDomain collection with a MemoryDomain including an InterleaveableSet for interleaving and an InterleaveableSet for no interleaving for the PMEM devices.  The MemoryDomain needs a reference to a MemoryChunksCollection with no members to allow configuration via a POST to the MemoryChunksCollection. A POST request to a collection can only create a single Member. To create multiple new Members, multiple POST requests are required.

InitialBoot shows the Memory and MemoryDomain at initial boot with all the PMEM devices configured as volatile.  It includes one MemoryDomain showing both PMEM devices in one InterleavableSet and each PMEM device in their own InterleaveableSet.

![Initial.png](https://github.com/DMTF/Redfish/blob/Fix-3555/mockups/public-pmem-configuration/_artwork/Initial.png?raw=true)

### Config-PMEM-2
Config-PMEM-2.json shows an example of two POSTs to the MemoryChunkCollection, one for each PMEM in the Memory Domain to create Memory Chunks not interleaved on each PMEM, PMEM Memory Chunk of size 4096 MiB. The remaining capacity, 122288MiB, will be configured as volatile. When the POST is processed, Regions will be allocated as appropriate with no interleaving for the PMEM Memory Chunk. This POST will result in the mockup Config-2-PMEM.

![Config-2.png](https://github.com/DMTF/Redfish/blob/Fix-3555/mockups/public-pmem-configuration/_artwork/Config-2.png?raw=true)

### Config-PMEM-3
Config-PMEM-3.json shows an example of one POST to the MemoryChunkCollection in the Memory Domain to create a PMEM Memory Chunk of size 8192 MiB interleaved across both PMEM Devices. The remaining 8192 MiB will be allocated as volatile. This POST will fail unless the caller performs a **DELETE** of the persistent MemoryChunk created with Config-PMEM-2.json. Regions will be allocated as appropriate. This POST will result in the mockup Config-3-PMEM.

![Config-3.png](https://github.com/DMTF/Redfish/blob/Fix-3555/mockups/public-pmem-configuration/_artwork/Config-3.png?raw=true)

### AddPMEM
AddPMEM shows a mockup of the same configuration as Config-3-PMEM with two new unconfigured 16GiB PMEM devices added on
the same memory controller.

![Add-PMEM.png](https://github.com/DMTF/Redfish/blob/Fix-3555/mockups/public-pmem-configuration/_artwork/Add-PMEM.png?raw=true)

### Config-PMEM-4
Config-PMEM-4.json shows an example of one POST to the MemoryChunkCollection in the Memory Domain to reconfigure all four PMEM devices as 32GiB persistent interleaved across all 4 PMEM devices. The remaining 32GiB will be configured volatile.  This requires a POST for a Memory Chunk of 32GiB persistent. The existing MemoryChunks will need to be deleted before this POST can be submitted. This POST will result in the mockup Config-4-PMEM.

![Config-4.png](https://github.com/DMTF/Redfish/blob/Fix-3555/mockups/public-pmem-configuration/_artwork/Config-4.png?raw=true)

