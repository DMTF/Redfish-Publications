Mockup of AEP NVDIMMs post configuration of request for adding a new AEP NVDIMM on the same
memory controller after performing Config-AEP-3

Memory shows the configured AEP NVDIMMs with the same configuration and a single new unconfigured
AEP NVDIMM.

The existing MemoryDomain shows a new InterleavableSet with all 3 AEP NVDIMMs as the best interleave and a new InterleaveableSet for the added unconfigured AEP NVDIMM. This allows the user to configure just the unconfigured NVDIMM or reconfigure all the NVDIMMs as interleaved or not. The MemoryChunks collection still shows the MemoryChunks for the configured AEP NVDIMMs.
