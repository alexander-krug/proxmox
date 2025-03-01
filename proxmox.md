set up the on-subscription PBS repo:
under "Administration" choose "Add" and select "No-Subscription" and click "Add"

create ZFS pool with 2x NVME SSD
1. choose a node with 2 available disks
1. under the node go to "Disks" and verify the disks are available (wipe if needed)
1. next, under "Disks" go to "ZFS" and click "Create: ZFS" (ensure there are two same sized disks, unlike in the screenshot)
![image](https://github.com/user-attachments/assets/ac689913-3190-4b59-b420-b3a68d64f3dc)
1. go to "Datacenter" -> "Storage" and "Add", choose "ZFS" and choose the pool just created, selecting the appropriate content types

Add proxmox backup server (PBS) as storage
"Datacenter" -> "Storage" -> "Add" choose "Proxmox Backup Server"
![image](https://github.com/user-attachments/assets/8970b4a4-23c5-4868-83df-687dde94b635)
(the fingerprint can be retrieved from the PBS server under dashboard, on the bottom right there is button named "Show Fingerprint")
