# Linux Volume Management (LVM)

## Task 1: Check Current Storage
Run:
- lsblk, pvs, vgs, lvs, df -h
<img width="1217" height="672" alt="1" src="https://github.com/user-attachments/assets/c1a16d43-8509-4c50-bebd-63049c8d8645" />


## Task 2: Create Physical Volume
- pvcreate /dev/nvme1n1
- pvs
<img width="897" height="482" alt="2" src="https://github.com/user-attachments/assets/e4181c6c-5ee9-466e-ac3a-7c2a338a3f0b" />


## Task 3: Create Volume Group
- vgcreate devops-vg /dev/nvme1n1
- vgs
<img width="922" height="143" alt="3" src="https://github.com/user-attachments/assets/f58f122f-eb22-4456-b195-ced441c2627c" />



## Task 4: Create Logical Volume
- lvcreate -L 500M -n app-data devops-vg
- lvs
<img width="1222" height="122" alt="4" src="https://github.com/user-attachments/assets/51643b91-e317-47d1-b276-e300e81e67eb" />


## Task 5: Format and Mount
- mkfs.ext4 /dev/devops-vg/app-data
- mkdir -p /mnt/app-data
- mount /dev/devops-vg/app-data /mnt/app-data
 df -h /mnt/app-data
<img width="1436" height="773" alt="5" src="https://github.com/user-attachments/assets/e0faeaf8-26e2-4256-a658-ca81045f6573" />


## Task 6: Extend the Volume
- lvextend -L +200M /dev/devops-vg/app-data
- resize2fs /dev/devops-vg/app-data
- df -h /mnt/app-data
<img width="1602" height="676" alt="6" src="https://github.com/user-attachments/assets/bec993a0-6a5d-4925-80c2-f157fb273665" />

---

## What I Learned

- Creating and attaching storage volumes using AWS EC2
- Setting up Physical Volumes (PV), Volume Groups (VG) and Logical Volumes (LV)
- Extending logical volumes and resizing file systems
