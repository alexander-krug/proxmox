replace 10.10.10.X with the respective IPs


make a mountpoint for the share

´´´mkdir -p /mnt/nfs_share´´´

mount the share

´´´10.10.10.155://export/proxmox-backup-server /mnt/nfs_share´´´

make it permanent 

´´´vi /etc/fstab´´´

paste: "10.10.10.155://export/proxmox-backup-server /mnt/nfs_share  nfs  defaults  0  0"
test it by doing:

´´´mount -a´´´


prepare the folder

´´´chown backup:backup /mnt/nfs_share && chmod 775 /mnt/nfs_share/´´´


now add the datastore

´´´proxmox-backup-manager datastore create whitebox_nfs_share /mnt/nfs_share´´´



troubleshooting

1. install nfs prerequisites 

´´´apt update´´´

´´´apt install nfs-common´´´


