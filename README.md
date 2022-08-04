Create 2 instances in 2 different availability zones.
Create new security group adding ssh, http, nfs.
we can also add user data.
Go to efs service.
create new file system.
In details, go to network---manage
Select mount target i.e. availability zones that we have selected when instances created.
Attach file system --select mount via IP
Attach security group to the selected availability zones.
Take SSH of both instances via mobaxterm.
1st machine --create directory
mkdir /test
cd /test
touch file{1..10}
ls
yum install amazon_efs_utils -y
sudo -i
mount -t efs (ID)(generated id in file system):/ /test
ls /test
df -hT
2nd machine
sudo -i
mkdir /demo
yum install amazon_efs_utils -y
mount -t efs(ID):/ /test
df -hT
cd /demo
ls
In 1st machine
Create files in /test
cd /test
touch file{1..10}
2nd machine
cd /demo
ls
