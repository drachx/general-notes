I am using VMWare on Mac during this test.
Please note that this is for learning purposes only. Do it at your own risk or do something else.

- Create new Custom VM as normal name it as "Win10Raw" or whatever you want it to have
- Open terminal
- Run: `$ sudo -s`
- Check which partition you wanted to use `$ diskutil list`. In this example I will just use a random disk named `disk22s4` - that is Disk #22 on Partition 4
- CD to VMware Library: `$ cd /Applications/VMware\ Fusion.app/Contents/Library/`
- Let's create VMDK to Raw disk22s4: `$ vmware-rawdislCreator create /dev/disk22 4 ~/VMs/Win10Raw/rawDiskFile ide` - this will create a raw disk under my newly created VM found at `~/VMs/Win10Raw`
- Let's inspect the disk: 
    ```
    $ cd ~/VMs/Win10Raw/
    $ ls -l
    ```
- Let's give it full permision: `$ chmod 777 rawDiskFile*`
- Now open VMWare app and modify settings of `Win10Raw`. Remove the auto created disk and add IDE `rawDiskFile.vmdk` or manually modify VMX file as below
    ```
    ide0:0.present = "TRUE"
    ide0:0.fileName = "rawDiskFile.vmdk"
    ide0:0.deviceType = "rawDisk"
    suspend.disabled = "TRUE"
    ```
- Install as usual
