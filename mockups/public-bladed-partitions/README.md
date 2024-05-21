# Multi-Blade Partition Enclosure Mockup:

## These mocks use Redfish Composability.

This service reports physically partitioned Systems within a MultiBlade Enclosure.  Partitionable resources are reported and managed using redfish CompositionService.
Individual blades are reported as ResourceBlocks.

Enclosure has 8 Blades and 2 Managers in redundant pair.
7 Blades are reported as "Compute" ResourceBlocks and 1 Storage Blade is reported as "Storage" ResourceBlock.
There are 3 “Physical Partitions”, managed by EnclosureManager and created through CompositionService defintions.
The mocks also report 2 Unused Blades and associated ResourceBlocks:

1.	ComposedPartition1 - Composed Partition with 1 BladeComputeBlock
2.	ComposedPartition2 - Composed Partition with 3 BladeComputeBlocks
3.  ComposedPartition3 - Composed Partition with 1 BladeComputeBlock and 1 BladeStorageBlock
