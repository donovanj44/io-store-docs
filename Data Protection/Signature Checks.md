<h3>Signature checks/ validation of data</h3>

<p>Main signature checks consist of validating the header and the compression blocks.</p>
<p>The current way they do this is by hashing the data on creation and storing that hash inside the TOC. On mount, the engine checks the hashes by hashing the data again and comparing the hashed data.</p>

<p>The creation of the hashes/ signatures is done inside of static method:</p>

```cpp
static FIoStatus CreateContainerSignature
```


<p>The validation of the hashes/ signatures is done inside of static method:</p>

```cpp
static FIoStatus ValidateContainerSignature
```

<a href="https://github.com/EpicGames/UnrealEngine/blob/release/Engine/Source/Runtime/Core/Private/IO/IoStore.cpp">Source link (IoStore.cpp)</a>
