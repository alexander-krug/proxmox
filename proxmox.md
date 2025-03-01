set up the on-subscription PBS repo:
under "Administration" choose "Add" and select "No-Subscription" and click "Add"

create ZFS pool with 2x NVME SSD
1. choose a node with 2 available disks
1. under the node go to "Disks" and verify the disks are available (wipe if needed)
1. next, under "Disks" go to "ZFS" and click "Create: ZFS" (ensure there are two same sized disks, unlike in the screenshot)
![image](https://github.com/user-attachments/assets/ac689913-3190-4b59-b420-b3a68d64f3dc)
1. go to "Datacenter" -> "Storage" and "Add", choose "ZFS" and choose the pool just created, selecting the appropriate content types

1. 
