# W7 - Operation

### Docker

In order to clean docker unused files (container, log, images and so on), this script run every day

```bash
echo "0 2 * * * sudo docker run --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /etc:/etc:ro spotify/docker-gc" | sudo tee /etc/cron.d/docker-gc > /dev/null
```

### Aumentare spazio disco su EC2 UBUNTU
Vedere il disco e òa sua occupazione con il comando df
ubuntu@ip-172-31-26-105:~$ df
Filesystem     1K-blocks     Used Available Use% Mounted on
udev              487552        0    487552   0% /dev
tmpfs             100212      732     99480   1% /run
/dev/xvda1      40593612 40561788     15440 100% /
tmpfs             501052        0    501052   0% /dev/shm
tmpfs               5120        0      5120   0% /run/lock
tmpfs             501052        0    501052   0% /sys/fs/cgroup
/dev/loop1         28800    28800         0 100% /snap/amazon-ssm-agent/2012
/dev/loop3         18432    18432         0 100% /snap/amazon-ssm-agent/1566
/dev/loop4        100096   100096         0 100% /snap/core/10126
/dev/loop0        100096   100096         0 100% /snap/core/10185
tmpfs             100208        0    100208   0% /run/user/1000
ubuntu@ip-172-31-26-105:~$ find / -size +256M

1) andare su Amazon EC2 e individuare il Volume corrisponedente
2) richiedere di aumentarlo
3) sulla macchina lanciare lsblk

ubuntu@ip-172-31-26-105:~/bck$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
loop0     7:0    0 97.8M  1 loop /snap/core/10185
loop1     7:1    0 28.1M  1 loop /snap/amazon-ssm-agent/2012
loop3     7:3    0   18M  1 loop /snap/amazon-ssm-agent/1566
loop4     7:4    0 97.7M  1 loop /snap/core/10126
xvda    202:0    0   40G  0 disk
└─xvda1 202:1    0   40G  0 part /


4) lanciare il comando   
   sudo growpart /dev/xvda 1 

Nell'esempio il disco è da 40GB
dopo aver assegnato 80 GB al disco il comando ls rispondrà:
ubuntu@ip-172-31-26-105:~/bck$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
loop0     7:0    0 97.8M  1 loop /snap/core/10185
loop1     7:1    0 28.1M  1 loop /snap/amazon-ssm-agent/2012
loop3     7:3    0   18M  1 loop /snap/amazon-ssm-agent/1566
loop4     7:4    0 97.7M  1 loop /snap/core/10126
xvda    202:0    0   80G  0 disk
└─xvda1 202:1    0   40G  0 part /


5) sudo resize2fs /dev/xvda1

ubuntu@ip-172-31-26-105:~/bck/ISPRA$ df
Filesystem     1K-blocks     Used Available Use% Mounted on
udev              487552        0    487552   0% /dev
tmpfs             100212      800     99412   1% /run
/dev/xvda1      81253764 39433052  41804328  49% /
tmpfs             501052        8    501044   1% /dev/shm
tmpfs               5120        0      5120   0% /run/lock
tmpfs             501052        0    501052   0% /sys/fs/cgroup
/dev/loop1         28800    28800         0 100% /snap/amazon-ssm-agent/2012
/dev/loop3         18432    18432         0 100% /snap/amazon-ssm-agent/1566
/dev/loop4        100096   100096         0 100% /snap/core/10126
/dev/loop0        100096   100096         0 100% /snap/core/10185
tmpfs             100208        0    100208   0% /run/user/1000




