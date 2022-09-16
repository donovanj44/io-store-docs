<h3>Container TOC data</h3>

<details>
    
<summary>Container TOC data</summary>
    
```cpp
struct FIoStoreTocResource
{
    enum { CompressionMethodNameLen = 32 };

    FIoStoreTocHeader Header;

    TArray<FIoChunkId> ChunkIds;

    TArray<FIoOffsetAndLength> ChunkOffsetLengths;

    TArray<int32> ChunkPerfectHashSeeds;

    TArray<int32> ChunkIndicesWithoutPerfectHash;

    TArray<FIoStoreTocCompressedBlockEntry> CompressionBlocks;

    TArray<FName> CompressionMethods;

    FSHAHash SignatureHash;

    TArray<FSHAHash> ChunkBlockSignatures;

    TArray<FIoStoreTocEntryMeta> ChunkMetas;

    TArray<uint8> DirectoryIndexBuffer;
};
```
</details>

<details>
    
<summary>I/O Store TOC header</summary>
    
```cpp
struct FIoStoreTocHeader
{
    static constexpr char TocMagicImg[] = "-==--==--==--==-";

    uint8	TocMagic[16];
    uint8	Version;
    uint8	Reserved0 = 0;
    uint16	Reserved1 = 0;
    uint32	TocHeaderSize;
    uint32	TocEntryCount;
    uint32	TocCompressedBlockEntryCount;
    uint32	TocCompressedBlockEntrySize;	// For sanity checking
    uint32	CompressionMethodNameCount;
    uint32	CompressionMethodNameLength;
    uint32	CompressionBlockSize;
    uint32	DirectoryIndexSize;
    uint32	PartitionCount = 0;
    FIoContainerId ContainerId;
    FGuid	EncryptionKeyGuid;
    EIoContainerFlags ContainerFlags;
    uint8	Reserved3 = 0;
    uint16	Reserved4 = 0;
    uint32	TocChunkPerfectHashSeedsCount = 0;
    uint64	PartitionSize = 0;
    uint32	TocChunksWithoutPerfectHashCount = 0;
    uint32	Reserved7 = 0;
    uint64	Reserved8[5] = { 0 };
};
```
</details>
