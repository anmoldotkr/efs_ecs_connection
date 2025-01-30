# efs_ecs_connection
 This repository will teach you how to mount an EFS to a specific directory in your container, where the application.log file will be generated. It also demonstrates how to copy that folder to your EFS under a specific directory and how to mount it locally to view the files in EFS.

 ---------------------------------------------
 🎯 Summary
Step	Command	Description
Install NFS Utilities	sudo apt install -y nfs-common	Required for mounting EFS
Create Mount Directory	sudo mkdir -p /mnt/efs	Creates a directory for EFS
Manually Mount EFS	sudo mount -t nfs4 -o nfsvers=4.1 ...	Mounts EFS to /mnt/efs
Check Mount Status	df -h	Verifies that EFS is mounted
Fix Permissions	sudo chown ubuntu:ubuntu /mnt/efs/application.log	Ensures user has write access
Enable Auto-Mount	Edit /etc/fstab	Ensures EFS mounts on reboot
Apply fstab Changes	sudo mount -a	Mounts all filesystems in /etc/fstab
Verify Auto-Mount	`df -h	grep efs`
