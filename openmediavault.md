clear usb stick of partitions using fdisk

create bootable usb
replace sdX with the device name sourced by using "sudo lsblk"
```sudo dd if=/mnt/chromeos/MyFiles/Downloads/iso-files/openmediavault_7.0-32-amd64.iso of=/dev/sdX bs=4M status=progress conv=fdatasync```

install openmediavault
take notes: 
- save credentials to apple keychain
- note the IP during installation, alternatively use nmap from a device in the same network e.g. 10.10.10.1/24 to scan 10.10.10.1-10.10.10.254

prepare the disk for the backup data
find the disk
```sudo lsblk```
clear it of partitions 
```sudo fdisk /dev/sda```
type "d" and hit enter, repeat until all partitions are deleted
type "n" and enter through the options to create one big partition for the next step
type "w" to write changes#

create a filesystem
```sudo mkfs.ext4 /dev/sda1```

under "Storage" -> "Shared folders"
next create a shared folder for native proxmox backups (only of the proxmox backup server VM)
also create a shared folder for proxmox backup server backups (of all VMs)
![image](https://github.com/user-attachments/assets/38c0423a-429d-4591-859a-a1c55c8674d8)

under "Services" -> "NFS" -> "Shares"
now create one NFS share per shared folder 
client for proxmox-backup-server = IP of proxmox backup server (PBS)
client for proxmox-native-backup = IP of proxmox server 
options for both "insecure, rw, subtree_check"

