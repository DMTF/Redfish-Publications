##Mockup of PMEM devices post configuration with Config-AEP-2.json

Memory shows the PMEM devices with two newly created Regions for each PMEM device NVDIMM, 4096MiB persistent, 12288MiB volatile.

MemoryDomains shows the MemoryDomains collection with a new Member.  MemoryDomains for best interleaved and not interleaved are not duplicated here, but they will exist in the model. Those MemoryDomains will never have any MemoryChunks, they are just used for configuration.

The new MemoryDomains collection Member shows the new MemoryChunks collection.

The new MemoryChunks collection Members, shows the two newly created persistent MemoryChunks, one for each PMEM device using the newly created persistent region on each PMEM device.  No MemoryChunk for the volatile regions.
