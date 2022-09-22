<h3>Container TOC data</h3>

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
