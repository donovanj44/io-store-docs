<p>First of all, you'll need to open FModel, load your game, and find the asset your trying to replace or modify.</p>
<p>For this example I'll use DefaultPickaxe.uasset, when editing an asset you can't change the length of the file/asset unless you change the summary of the asset, which is located at the top, and some TOC information; a ChunkOffsetAndLength entry, and a CompressedBlock entry(s).</p>

<h3>Basic modifcation</h3>
<p>String editing is by far the easiest way to modify assets. FSoftObjectPaths are always located within the asset inside the NameMap, which is easily accessable by just pasting over your (smaller) string and adding some zeroes into the hex field until you've filled up the rest of the old string.</p>
<p>TODO... add pictures</p>

<h3>Above average modifcation</h3>
<p>TODO... bigger strings</p>

<h3>Advanced modifcation</h3>
<p>TODO... editing file size</p>

<h3>Super advanced modifcation</h3>
<p>TODO... recreation of the enitre asset programmatically</p>
