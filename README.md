<h1>I/O Store docs</h1>

<h3>Welcome to my documentation of I/O Store and how Unreal Engine 5 stores data in ucas’, utocs, and uassets.</h3>

<h4>File types</h4>
<ul>
  <li>.ucas</li>
  <li>.utoc</li>
</ul>

<h3>The UCAS</h3>
<p>Firstly we’ll start with the ucas, the container for all of actual data (models, images, animations), basically a ucas is a list of datas (usually compressed) for the game to read. These may contain uassets, ubulks, uptnl, and sometimes INIs.</p>

<h4>Partitions</h4>
<p>I/O containers (ucas) can be partitioned into sections. Fortnite for example has a I/O container partitioned into five different files as of the update <b>++Fortnite+Release-21.51-CL-21735703-Windows</b></p>

<h5>Why?</h5>
<p>Why are these files partitioned you may ask? Well firstly it’s so that Windows can even store these files, although a New Technology File System (NTFS) disk’s max file size is 256TB with a max disk size of 8 Petabytes, a File Allocation Table (FAT32) disk can only store a file as big as 4.29GB with a astonishingly low disk size of only 2TB. Kinda makes sense through for the fact the FAT32 was introduced in 1996. 
</p>

<h3>The UTOC</h3>
<p>Anyway, the step after the bytes are allocated, is to actually write the data. I’ve already explained most of what a ucas is used for, however it is time to explain how a utoc works.</p>

<p>Basically a utoc (I/O dispatcher) is used as a list of pointers, containing both the size and offset of the data inside of the I/O container, virtually that's all it's used for, but because they overcomplicate it, so I'll have to explain more.</p>

<h4>What's in the UTOC?</h4>
<p>Inside of the utoc, starting at offset zero, we have the header, the first part of the header contains a file magic declaration to insure that what Unreal Engine is reading is in fact a I/O store file (not just named `.utoc`). This header also contains the version of the I/O store system (I’m gonna refer to this as <b>I/O-SS</b> from now on), and much more that I'll talk about in the subpages.</p>
