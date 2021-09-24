# fdisk -l


Add two EBS volumes to ec2 instance then enter fdisk -l

#fdisk / diskname

#p : print
#n  : new partition creation
#p  : primary partition
#1  : enter 1(4 we have)

default enter 
memory size like 5GB(we can select)

#t : in memory attach LVM
#8e : hexa number for lvm cretaion
#p  : print 
#wq---save

attach partition to kernal

#partprobe /dev/xvdf

create phisical volume

#pvcreate /dev/xvdf1 /dev/xvdg1
#pvs  (list)
#vgcreate VG0 /dev/xvdf1  /dev/xvdg1
#vgs  (list)

lv creating

#lvcreate -n lv0 -L +5G VG0 (lv0-lvm name)

#lvdisplay /dev/VG0/lv0 (lvm display)

#mkfs.ext4 /dev/VG0/lv0 (creating file system attach to filesystem)
#mkdir /kernal (creating directory)
#mount /dev/VG0/lv0 /kernal ( mounting lvm into directory)

#df -h 

#cd kernal

we can store data & work .
