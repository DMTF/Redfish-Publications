This mockup shows the configuration of PMEM devices in a system at initial boot.
A real server would have DIMMs, but they are not included in this mock-up for simplicity.

Configuration requires a POST to the MemoryChunksCollection referenced in a MemoryDomain. The mockup shows a MemoryDomainsCollection with a MemoryDomain with InterleaveableSets for interleave and for each individual PMEM device for no interleave with a reference to a MemoryChunksCollection that is empty, to allow the user to do the POST to the empty MemoryChunksCollection to configure regions and chunks on the PMEM devices.
