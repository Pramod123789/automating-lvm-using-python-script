import os
import sys
import pyfiglet
from termcolor import colored
from pyfiglet import figlet_format

print("**************************************************************************************")
print((colored(figlet_format("Welome To Logical Volume Manager","standard"), color='blue')))
print("**************************************************************************************")
disk_name = input("Enter the Name of Disk :  ")
os.system(f"pvcreate {disk_name}")
os.system(f"pvdisplay {disk_name}")
vg_name = input("Enter the Name of the Volume Group To be Created ")
os.system(f"vgcreate {vg_name} {disk_name}")
os.system(f"vgdisplay {vg_name}")
lv_name = input("Enter Name of the LVM To be Created :")
size = input(f"Enter the size: ")
os.system(f"lvcreate --size {size} --name {lv_name} {vg_name}")
os.system(f"mkfs.ext4 /dev/{vg_name}/{lv_name}")
mount_point=input("Enter the directory Name to be mounted:")
os.system(f"mkdir /{mount_point}")
os.system(f"mount /dev/{vg_name}/{lv_name} /{mount_point}")
os.system("df -hT")
i_size = input(f"Enter the size to be increased:")
os.system(f"lvextend --size +{i_size} /dev/{vg_name}/{lv_name}")
os.system(f"resize2fs /dev/{vg_name}/{lv_name}")
os.system("df -hT")
