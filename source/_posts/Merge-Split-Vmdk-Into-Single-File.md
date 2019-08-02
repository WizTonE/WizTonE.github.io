---
title: Merge Split Vmdk Into Single File
tags:
  - VMware
date: 2019-08-02 05:31:52
---


# Merge split vmdk files into single one.

VMware Disk I/O performance tunning

<!-- More -->

In the very beginning when initial a vm with VMware, it will ask you to choose two different storage types, split file and single file mode.

Split files are very useful to put them on filesystem with file size limit according the disk partition format (FAT32,.etc).

For better performance you can use single file and preallocated disk.

If you choosed the split one and got the performance issue in your vm, you probablly might convert the vmdk files into the monolithic mode.

Here is the steps:

* Shutdown the VM.

* Open the VM folder
{% asset_img 01.png %}

* Type cmd in the path then enter
{% asset_img 02.png %}

* Type c:\Program Files (x86)\VMware\VMware Workstation vmware-vdiskmanager.exe -r "Windows 10 x64.vmdk" -t 0 NewMonolithic.vmdk

* Wait the "Convert" to 100%.

* Delete those old 00xx.vmdk files, then rename NewMonolithic.vmdk to Windows 10 x64.vmdk

* Power on the VM, the VM should run faster then before.

# Link
---
- {% link "HOW TO MERGE MULTIPLE VMDK’S INTO SINGLE VMDK" https://vmexpo.wordpress.com/2014/04/15/how-to-merge-multiple-vmdks-into-single-vmdk/ %}

- {% link "Changing a monolithic disk to a split disk in VMware Workstation " https://kb.vmware.com/s/article/2006898 %}