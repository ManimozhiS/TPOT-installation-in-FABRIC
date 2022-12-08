# TPOT-installation-in-FABRIC
This repo contains our initial attempt in installing the T-POT honeypot in a research testbed FABRIC

(base) fabric@jupyter-msekar3-40asu-2eedu:~/work$ ssh - i ~/work/fabric_config/sliver -F ~/work/fabric_config/ssh_config ubuntu@11.22.33.44
ssh: Could not resolve hostname -: Name or service not known
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work$ ls
config.txt  fabric_config  fabric-notebooks  jupyter-examples-rel1.3.1  jupyter-examples-rel1.3.3  lab2  lost+found  tpotce  Untitled.ipynb
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work$ cd fabric_config
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ ls
bastion  bastion.pub  fabric_rc  slice_key  slice_key.pub  sliver  sliver.pub  ssh_config
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ vim ssh_config
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ ssh -F ssh_config -i sliver  ubuntu@129.114.110.110
Warning: Permanently added 'bastion-1.fabric-testbed.net,152.54.15.12' (ECDSA) to the list of known hosts.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0660 for '/home/fabric/work/fabric_config/bastion' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "/home/fabric/work/fabric_config/bastion": bad permissions
msekar3_0000028786@bastion-1.fabric-testbed.net: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
kex_exchange_identification: Connection closed by remote host
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ chmod 600 sliver
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ ssh -F ssh_config -i sliver  ubuntu@129.114.110.110
Warning: Permanently added 'bastion-1.fabric-testbed.net,152.54.15.12' (ECDSA) to the list of known hosts.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0660 for '/home/fabric/work/fabric_config/bastion' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "/home/fabric/work/fabric_config/bastion": bad permissions
msekar3_0000028786@bastion-1.fabric-testbed.net: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
kex_exchange_identification: Connection closed by remote host
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ chmod 600 bastion
(base) fabric@jupyter-msekar3-40asu-2eedu:~/work/fabric_config$ ssh -F ssh_config -i sliver  ubuntu@129.114.110.110
Warning: Permanently added 'bastion-1.fabric-testbed.net,152.54.15.12' (ECDSA) to the list of known hosts.
Warning: Permanently added '129.114.110.110' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-97-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sun Nov 27 00:38:41 UTC 2022

  System load:  0.0               Processes:             128
  Usage of /:   1.4% of 96.75GB   Users logged in:       0
  Memory usage: 1%                IPv4 address for ens3: 10.20.5.75
  Swap usage:   0%

 * Strictly confined Kubernetes makes edge and IoT secure. Learn how MicroK8s
   just raised the bar for easy, resilient and secure K8s cluster deployment.

   https://ubuntu.com/engage/secure-kubernetes-at-the-edge

1 update can be applied immediately.
To see these additional updates run: apt list --upgradable


The list of available updates is more than a week old.
To check for new updates run: sudo apt update
New release '22.04.1 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~$ apt-get -y update && apt-get -y install git
Reading package lists... Done
E: Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)
E: Unable to lock directory /var/lib/apt/lists/
W: Problem unlinking the file /var/cache/apt/pkgcache.bin - RemoveCaches (13: Permission denied)
W: Problem unlinking the file /var/cache/apt/srcpkgcache.bin - RemoveCaches (13: Permission denied)
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~$ sudo apt-get -y update && apt-get -y install git
Get:1 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Hit:2 http://nova.clouds.archive.ubuntu.com/ubuntu focal InRelease
Get:3 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:4 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [1860 kB]
Get:5 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Get:6 http://security.ubuntu.com/ubuntu focal-security/main Translation-en [306 kB]
Get:7 http://security.ubuntu.com/ubuntu focal-security/main amd64 c-n-f Metadata [11.2 kB]
Get:8 http://security.ubuntu.com/ubuntu focal-security/restricted amd64 Packages [1332 kB]
Get:9 http://security.ubuntu.com/ubuntu focal-security/restricted Translation-en [188 kB]
Get:10 http://security.ubuntu.com/ubuntu focal-security/restricted amd64 c-n-f Metadata [640 B]
Get:11 http://security.ubuntu.com/ubuntu focal-security/universe amd64 Packages [773 kB]
Get:12 http://security.ubuntu.com/ubuntu focal-security/universe Translation-en [148 kB]
Get:13 http://security.ubuntu.com/ubuntu focal-security/universe amd64 c-n-f Metadata [16.8 kB]
Get:14 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [22.2 kB]
Get:15 http://security.ubuntu.com/ubuntu focal-security/multiverse Translation-en [5400 B]
Get:16 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 c-n-f Metadata [516 B]
Get:17 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe amd64 Packages [8628 kB]
Get:18 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe Translation-en [5124 kB]
Get:19 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe amd64 c-n-f Metadata [265 kB]
Get:20 http://nova.clouds.archive.ubuntu.com/ubuntu focal/multiverse amd64 Packages [144 kB]
Get:21 http://nova.clouds.archive.ubuntu.com/ubuntu focal/multiverse Translation-en [104 kB]
Get:22 http://nova.clouds.archive.ubuntu.com/ubuntu focal/multiverse amd64 c-n-f Metadata [9136 B]
Get:23 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [2242 kB]
Get:24 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/main Translation-en [390 kB]
Get:25 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [16.1 kB]
Get:26 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [1424 kB]
Get:27 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/restricted Translation-en [202 kB]
Get:28 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/restricted amd64 c-n-f Metadata [636 B]
Get:29 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [1004 kB]
Get:30 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/universe Translation-en [233 kB]
Get:31 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/universe amd64 c-n-f Metadata [23.2 kB]
Get:32 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [24.4 kB]
Get:33 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/multiverse Translation-en [7316 B]
Get:34 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 c-n-f Metadata [592 B]
Get:35 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/main amd64 Packages [45.7 kB]
Get:36 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/main Translation-en [16.3 kB]
Get:37 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/main amd64 c-n-f Metadata [1420 B]
Get:38 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/restricted amd64 c-n-f Metadata [116 B]
Get:39 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [24.0 kB]
Get:40 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/universe Translation-en [16.0 kB]
Get:41 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/universe amd64 c-n-f Metadata [860 B]
Get:42 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports/multiverse amd64 c-n-f Metadata [116 B]
Fetched 24.9 MB in 4s (5845 kB/s)                           
Reading package lists... Done
E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~$ git clone https://github.com/telekom-security/tpotce
Cloning into 'tpotce'...
remote: Enumerating objects: 14133, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (41/41), done.
remote: Total 14133 (delta 18), reused 49 (delta 16), pack-reused 14074
Receiving objects: 100% (14133/14133), 217.53 MiB | 65.25 MiB/s, done.
Resolving deltas: 100% (7859/7859), done.
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~$ cd tpotce/
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ cp iso/installer/tpot.conf.dist /root/tpot.conf
cp: failed to access '/root/tpot.conf': Permission denied
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ sudo cp iso/installer/tpot.conf.dist /root/tpot.conf
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ ./install.sh --conf=/root/tpot.conf

### Checking for root: [ NOT OK ]
### Please run as root.
### Example: sudo ./install.sh
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ sudo ./install.sh --conf=/root/tpot.conf

### Checking for root: [ OK ]
### Installing apt-fast
Hit:1 http://nova.clouds.archive.ubuntu.com/ubuntu focal InRelease
Hit:2 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:3 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu focal-security InRelease
Reading package lists... Done
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libaria2-0 libc-ares2 libssh2-1
The following NEW packages will be installed:
  aria2 libaria2-0 libc-ares2 libssh2-1
0 upgraded, 4 newly installed, 0 to remove and 181 not upgraded.
Need to get 1552 kB of archives.
After this operation, 6234 kB of additional disk space will be used.
Get:1 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates/main amd64 libc-ares2 amd64 1.15.0-1ubuntu0.1 [38.2 kB]
Get:2 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe amd64 libssh2-1 amd64 1.8.0-2.1build1 [75.4 kB]
Get:3 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe amd64 libaria2-0 amd64 1.35.0-1build1 [1082 kB]
Get:4 http://nova.clouds.archive.ubuntu.com/ubuntu focal/universe amd64 aria2 amd64 1.35.0-1build1 [356 kB]
Fetched 1552 kB in 1s (2825 kB/s)
Selecting previously unselected package libc-ares2:amd64.
(Reading database ... 63577 files and directories currently installed.)
Preparing to unpack .../libc-ares2_1.15.0-1ubuntu0.1_amd64.deb ...
Unpacking libc-ares2:amd64 (1.15.0-1ubuntu0.1) ...
Selecting previously unselected package libssh2-1:amd64.
Preparing to unpack .../libssh2-1_1.8.0-2.1build1_amd64.deb ...
Unpacking libssh2-1:amd64 (1.8.0-2.1build1) ...
Selecting previously unselected package libaria2-0:amd64.
Preparing to unpack .../libaria2-0_1.35.0-1build1_amd64.deb ...
Unpacking libaria2-0:amd64 (1.35.0-1build1) ...
Selecting previously unselected package aria2.
Preparing to unpack .../aria2_1.35.0-1build1_amd64.deb ...
Unpacking aria2 (1.35.0-1build1) ...
Setting up libc-ares2:amd64 (1.15.0-1ubuntu0.1) ...
Setting up libssh2-1:amd64 (1.8.0-2.1build1) ...
Setting up libaria2-0:amd64 (1.35.0-1build1) ...
Setting up aria2 (1.35.0-1build1) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for libc-bin (2.31-0ubuntu9.2) ...
--2022-11-27 00:41:28--  https://raw.githubusercontent.com/ilikenwf/apt-fast/master/apt-fast
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.111.133, 185.199.110.133, 185.199.108.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.111.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 22293 (22K) [text/plain]
Saving to: ‘/usr/local/sbin/apt-fast’

/usr/local/sbin/apt-fast                   100%[=======================================================================================>]  21.77K  --.-KB/s    in 0.001s  

2022-11-27 00:41:28 (23.4 MB/s) - ‘/usr/local/sbin/apt-fast’ saved [22293/22293]

--2022-11-27 00:41:28--  https://raw.githubusercontent.com/ilikenwf/apt-fast/master/apt-fast.conf
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.111.133, 185.199.110.133, 185.199.108.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.111.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4900 (4.8K) [text/plain]
Saving to: ‘/etc/apt-fast.conf’

/etc/apt-fast.conf                         100%[=======================================================================================>]   4.79K  --.-KB/s    in 0s      

2022-11-27 00:41:28 (58.4 MB/s) - ‘/etc/apt-fast.conf’ saved [4900/4900]

### Checking for installer dependencies: [ NOW INSTALLING ]
Hit:1 http://nova.clouds.archive.ubuntu.com/ubuntu focal InRelease
Hit:2 http://security.ubuntu.com/ubuntu focal-security InRelease
Hit:3 http://nova.clouds.archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:4 http://nova.clouds.archive.ubuntu.com/ubuntu focal-backports InRelease
Reading package lists... Done


11/27 00:41:30 [NOTICE] Downloading 17 item(s)

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libcrack2_2.9.6-3.2_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libcrack2_2.9.6-3.2_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libaprutil1_1.6.1-4ubuntu2_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libaprutil1_1.6.1-4ubuntu2_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/apache2-utils_2.4.41-4ubuntu3.12_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/apache2-utils_2.4.41-4ubuntu3.12_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libapr1_1.6.5-1ubuntu1_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libapr1_1.6.5-1ubuntu1_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/cracklib-runtime_2.9.6-3.2_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/cracklib-runtime_2.9.6-3.2_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/grc_1.11.3-1_all.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/grc_1.11.3-1_all.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/curl_7.68.0-1ubuntu2.14_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/curl_7.68.0-1ubuntu2.14_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/figlet_2.2.5-3_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/figlet_2.2.5-3_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libcurl4_7.68.0-1ubuntu2.14_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libcurl4_7.68.0-1ubuntu2.14_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/dialog_1.3-20190808-1_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/dialog_1.3-20190808-1_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libpq5_12.12-0ubuntu0.20.04.1_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libpq5_12.12-0ubuntu0.20.04.1_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libpq-dev_12.12-0ubuntu0.20.04.1_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libpq-dev_12.12-0ubuntu0.20.04.1_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/toilet_0.3-1.2_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/toilet_0.3-1.2_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/net-tools_1.60+git20180626.aebd88e-1ubuntu1_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/net-tools_1.60+git20180626.aebd88e-1ubuntu1_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/libcaca0_0.99.beta19-2.1ubuntu1.20.04.2_amd64.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/libcaca0_0.99.beta19-2.1ubuntu1.20.04.2_amd64.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/wamerican_2018.04.16-1_all.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/wamerican_2018.04.16-1_all.deb

11/27 00:41:31 [NOTICE] Verification finished successfully. file=/var/cache/apt/apt-fast/toilet-fonts_0.3-1.2_all.deb

11/27 00:41:31 [NOTICE] Download complete: /var/cache/apt/apt-fast/toilet-fonts_0.3-1.2_all.deb

Download Results:
gid   |stat|avg speed  |path/URI
======+====+===========+=======================================================
1b6c4d|OK  |   468KiB/s|/var/cache/apt/apt-fast/libcrack2_2.9.6-3.2_amd64.deb
336924|OK  |   661KiB/s|/var/cache/apt/apt-fast/libaprutil1_1.6.1-4ubuntu2_amd64.deb
5262d3|OK  |   649KiB/s|/var/cache/apt/apt-fast/apache2-utils_2.4.41-4ubuntu3.12_amd64.deb
bf4e58|OK  |   675KiB/s|/var/cache/apt/apt-fast/libapr1_1.6.5-1ubuntu1_amd64.deb
f0efc4|OK  |   811KiB/s|/var/cache/apt/apt-fast/cracklib-runtime_2.9.6-3.2_amd64.deb
e95ab4|OK  |   3.8MiB/s|/var/cache/apt/apt-fast/grc_1.11.3-1_all.deb
d7d99c|OK  |   1.1MiB/s|/var/cache/apt/apt-fast/curl_7.68.0-1ubuntu2.14_amd64.deb
036f3f|OK  |   1.3MiB/s|/var/cache/apt/apt-fast/figlet_2.2.5-3_amd64.deb
8af704|OK  |   1.8MiB/s|/var/cache/apt/apt-fast/libcurl4_7.68.0-1ubuntu2.14_amd64.deb
d8684f|OK  |   1.7MiB/s|/var/cache/apt/apt-fast/dialog_1.3-20190808-1_amd64.deb
1cb22e|OK  |   3.4MiB/s|/var/cache/apt/apt-fast/libpq5_12.12-0ubuntu0.20.04.1_amd64.deb
7bd6c2|OK  |   3.9MiB/s|/var/cache/apt/apt-fast/libpq-dev_12.12-0ubuntu0.20.04.1_amd64.deb
7828ee|OK  |   5.7MiB/s|/var/cache/apt/apt-fast/toilet_0.3-1.2_amd64.deb
1a3209|OK  |   6.2MiB/s|/var/cache/apt/apt-fast/net-tools_1.60+git20180626.aebd88e-1ubuntu1_amd64.deb
a94948|OK  |   1.6MiB/s|/var/cache/apt/apt-fast/libcaca0_0.99.beta19-2.1ubuntu1.20.04.2_amd64.deb
d2ccc3|OK  |   4.8MiB/s|/var/cache/apt/apt-fast/wamerican_2018.04.16-1_all.deb
0201aa|OK  |   6.9MiB/s|/var/cache/apt/apt-fast/toilet-fonts_0.3-1.2_all.deb

Status Legend:
(OK):download completed.
Reading package lists... Done
Building dependency tree       
Reading state information... Done
fuse is already the newest version (2.9.9-3).
fuse set to manually installed.
lsb-release is already the newest version (11.1.0ubuntu2).
lsb-release set to manually installed.
aria2 is already the newest version (1.35.0-1build1).
software-properties-common is already the newest version (0.99.9.8).
software-properties-common set to manually installed.
The following additional packages will be installed:
  libapr1 libaprutil1 libcaca0 libcurl4 libpq5 toilet-fonts wamerican
Suggested packages:
  postgresql-doc-12
The following NEW packages will be installed:
  apache2-utils cracklib-runtime dialog figlet grc libapr1 libaprutil1 libcaca0 libcrack2 libpq-dev libpq5 net-tools toilet toilet-fonts wamerican
The following packages will be upgraded:
  curl libcurl4
2 upgraded, 15 newly installed, 0 to remove and 179 not upgraded.
Need to get 0 B/2819 kB of archives.
After this operation, 8733 kB of additional disk space will be used.
Preconfiguring packages ...
Selecting previously unselected package libapr1:amd64.
(Reading database ... 63661 files and directories currently installed.)
Preparing to unpack .../00-libapr1_1.6.5-1ubuntu1_amd64.deb ...
Unpacking libapr1:amd64 (1.6.5-1ubuntu1) ...
Selecting previously unselected package libaprutil1:amd64.
Preparing to unpack .../01-libaprutil1_1.6.1-4ubuntu2_amd64.deb ...
Unpacking libaprutil1:amd64 (1.6.1-4ubuntu2) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../02-apache2-utils_2.4.41-4ubuntu3.12_amd64.deb ...
Unpacking apache2-utils (2.4.41-4ubuntu3.12) ...
Selecting previously unselected package libcrack2:amd64.
Preparing to unpack .../03-libcrack2_2.9.6-3.2_amd64.deb ...
Unpacking libcrack2:amd64 (2.9.6-3.2) ...
Selecting previously unselected package cracklib-runtime.
Preparing to unpack .../04-cracklib-runtime_2.9.6-3.2_amd64.deb ...
Unpacking cracklib-runtime (2.9.6-3.2) ...
Preparing to unpack .../05-curl_7.68.0-1ubuntu2.14_amd64.deb ...
Unpacking curl (7.68.0-1ubuntu2.14) over (7.68.0-1ubuntu2.7) ...
Preparing to unpack .../06-libcurl4_7.68.0-1ubuntu2.14_amd64.deb ...
Unpacking libcurl4:amd64 (7.68.0-1ubuntu2.14) over (7.68.0-1ubuntu2.7) ...
Selecting previously unselected package dialog.
Preparing to unpack .../07-dialog_1.3-20190808-1_amd64.deb ...
Unpacking dialog (1.3-20190808-1) ...
Selecting previously unselected package figlet.
Preparing to unpack .../08-figlet_2.2.5-3_amd64.deb ...
Unpacking figlet (2.2.5-3) ...
Selecting previously unselected package grc.
Preparing to unpack .../09-grc_1.11.3-1_all.deb ...
Unpacking grc (1.11.3-1) ...
Selecting previously unselected package libcaca0:amd64.
Preparing to unpack .../10-libcaca0_0.99.beta19-2.1ubuntu1.20.04.2_amd64.deb ...
Unpacking libcaca0:amd64 (0.99.beta19-2.1ubuntu1.20.04.2) ...
Selecting previously unselected package libpq5:amd64.
Preparing to unpack .../11-libpq5_12.12-0ubuntu0.20.04.1_amd64.deb ...
Unpacking libpq5:amd64 (12.12-0ubuntu0.20.04.1) ...
Selecting previously unselected package libpq-dev.
Preparing to unpack .../12-libpq-dev_12.12-0ubuntu0.20.04.1_amd64.deb ...
Unpacking libpq-dev (12.12-0ubuntu0.20.04.1) ...
Selecting previously unselected package net-tools.
Preparing to unpack .../13-net-tools_1.60+git20180626.aebd88e-1ubuntu1_amd64.deb ...
Unpacking net-tools (1.60+git20180626.aebd88e-1ubuntu1) ...
Selecting previously unselected package toilet-fonts.
Preparing to unpack .../14-toilet-fonts_0.3-1.2_all.deb ...
Unpacking toilet-fonts (0.3-1.2) ...
Selecting previously unselected package toilet.
Preparing to unpack .../15-toilet_0.3-1.2_amd64.deb ...
Unpacking toilet (0.3-1.2) ...
Selecting previously unselected package wamerican.
Preparing to unpack .../16-wamerican_2018.04.16-1_all.deb ...
Unpacking wamerican (2018.04.16-1) ...
Setting up net-tools (1.60+git20180626.aebd88e-1ubuntu1) ...
Setting up toilet-fonts (0.3-1.2) ...
Setting up libcaca0:amd64 (0.99.beta19-2.1ubuntu1.20.04.2) ...
Setting up toilet (0.3-1.2) ...
update-alternatives: using /usr/bin/figlet-toilet to provide /usr/bin/figlet (figlet) in auto mode
Setting up libpq5:amd64 (12.12-0ubuntu0.20.04.1) ...
Setting up libapr1:amd64 (1.6.5-1ubuntu1) ...
Setting up libpq-dev (12.12-0ubuntu0.20.04.1) ...
Setting up dialog (1.3-20190808-1) ...
Setting up wamerican (2018.04.16-1) ...
Setting up figlet (2.2.5-3) ...
update-alternatives: using /usr/bin/figlet-figlet to provide /usr/bin/figlet (figlet) in auto mode
Setting up libcrack2:amd64 (2.9.6-3.2) ...
Setting up libcurl4:amd64 (7.68.0-1ubuntu2.14) ...
Setting up grc (1.11.3-1) ...
Setting up curl (7.68.0-1ubuntu2.14) ...
Setting up libaprutil1:amd64 (1.6.1-4ubuntu2) ...
Setting up cracklib-runtime (2.9.6-3.2) ...
Setting up apache2-utils (2.4.41-4ubuntu3.12) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for libc-bin (2.31-0ubuntu9.2) ...
Aborting. Debian focal is not supported.

ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ cd iso/installer
ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce/iso/installer$ vi ./install.sh 



###Edit install.sh file under iso/installer/install.sh

line 21

myLSB_STABLE_SUPPORTED="stretch buster"

change it to

 myLSB_STABLE_SUPPORTED="stretch buster focal"
:wq

ubuntu@8fc45dcf-d94c-4043-8b9b-4c7ebbc4022d-node1:~/tpotce$ sudo ./install.sh --conf=/root/tpot.conf
Setting up node-readable-stream (3.4.0-2) ...
Setting up node-ssri (7.1.0-2) ...
Setting up node-through2 (3.0.1-2) ...
Setting up node-lru-cache (5.1.1-5) ...
Setting up node-bcrypt-pbkdf (1.0.2-1) ...
Setting up node-promise-retry (1.1.1-4) ...
Setting up libxmu6:amd64 (2:1.1.3-0ubuntu1) ...
Setting up libpython3-dev:amd64 (3.8.2-0ubuntu2) ...
Setting up node-end-of-stream (1.4.4-1) ...
Setting up libstdc++-9-dev:amd64 (9.4.0-1ubuntu1~20.04.1) ...
Setting up node-pump (3.0.0-2) ...
Setting up node-write-file-atomic (3.0.3-1) ...
Setting up node-columnify (1.5.4-1) ...
Setting up node-jsprim (1.4.1-1) ...
Setting up node-flush-write-stream (2.0.0-2) ...
Setting up node-are-we-there-yet (1.1.5-1) ...
Setting up node-find-up (4.1.0-2) ...
Setting up network-manager (1.22.10-1ubuntu2.3) ...
Created symlink /etc/systemd/system/dbus-org.freedesktop.nm-dispatcher.service → /lib/systemd/system/NetworkManager-dispatcher.service.
Created symlink /etc/systemd/system/network-online.target.wants/NetworkManager-wait-online.service → /lib/systemd/system/NetworkManager-wait-online.service.
Created symlink /etc/systemd/system/multi-user.target.wants/NetworkManager.service → /lib/systemd/system/NetworkManager.service.
Setting up libxaw7:amd64 (2:1.0.13-1) ...
Setting up x11-xserver-utils (7.7+8) ...
Setting up gcc (4:9.3.0-1ubuntu2) ...
Setting up node-duplexify (4.1.1-1) ...
Setting up node-spdx-correct (3.1.0-1) ...
Setting up network-manager-pptp (1.2.8-2) ...
Setting up node-cross-spawn (5.1.0-2) ...
Setting up node-ansi-styles (4.2.1-1) ...
Setting up node-glob (7.1.6-1) ...
Setting up node-get-stream (4.1.0-1) ...
Setting up node-pumpify (2.0.1-1) ...
Setting up node-widest-line (3.1.0-1) ...
Setting up node-got (7.1.0-1) ...
Setting up xclip (0.13-1) ...
Setting up node-chalk (2.4.2-1) ...
Setting up g++-9 (9.4.0-1ubuntu1~20.04.1) ...
Setting up node-configstore (5.0.1-1) ...
Setting up node-registry-url (3.1.0-1) ...
Setting up python3.8-dev (3.8.10-0ubuntu1~20.04.5) ...
Setting up node-registry-auth-token (3.3.1-1) ...
Setting up g++ (4:9.3.0-1ubuntu2) ...
update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
Setting up x11-utils (7.7+5) ...
Setting up build-essential (12.8ubuntu1.1) ...
Setting up node-wide-align (1.1.3-1) ...
Setting up node-ansi-align (3.0.0-1) ...
Setting up node-rimraf (2.6.3-1) ...
Setting up node-sshpk (1.16.1+dfsg-2) ...
Setting up node-bl (4.0.0-2) ...
Setting up cockpit-networkmanager (215-1) ...
Setting up node-validate-npm-package-license (3.0.4-1) ...
Setting up node-stream-each (1.2.3-1) ...
Setting up node-mississippi (3.0.0-1) ...
Setting up node-execa (0.10.0+dfsg-1) ...
Setting up node-copy-concurrently (1.0.5-4) ...
Setting up node-move-concurrently (1.0.1-2) ...
Setting up node-term-size (1.2.0+dfsg-2) ...
Setting up node-os-locale (4.0.0-1) ...
Setting up node-http-signature (1.3.2-1) ...
Setting up node-fs-vacuum (1.2.10-3) ...
Setting up node-gauge (2.7.4-1) ...
Setting up node-wrap-ansi (4.0.0-2) ...
Setting up node-normalize-package-data (2.5.0-1) ...
Setting up python3-dev (3.8.2-0ubuntu2) ...
Setting up node-boxen (4.2.0-2) ...
Setting up node-package-json (4.0.1-1) ...
Setting up node-latest-version (3.1.0-1) ...
Setting up node-request (2.88.1-4) ...
Setting up node-npmlog (4.1.2-2) ...
Setting up node-cliui (4.1.0-2) ...
Setting up node-yargs (15.3.0-1) ...
Setting up node-cacache (11.3.3-2) ...
Setting up node-read-package-json (2.1.1-1) ...
Setting up node-gyp (6.1.0-3) ...
Setting up node-libnpx (10.2.1-2) ...
Setting up npm (6.14.4+ds-1ubuntu2) ...
Setting up libwww-perl (6.43-1) ...
Setting up liblwp-protocol-https-perl (6.07-2ubuntu2) ...
Setting up libxml-parser-perl (2.46-1) ...
Setting up libxml-twig-perl (1:3.50-2) ...
Setting up libnet-dbus-perl (1.2.0-1) ...
Processing triggers for ufw (0.36-6ubuntu1) ...
Processing triggers for systemd (245.4-4ubuntu3.19) ...
Processing triggers for man-db (2.9.1-1) ...
Processing triggers for dbus (1.12.16-2ubuntu2.3) ...
Processing triggers for mime-support (3.64ubuntu1) ...
Processing triggers for libc-bin (2.31-0ubuntu9.9) ...
### Removing and holding back problematic packages ...
Reading package lists...
Building dependency tree...
Reading state information...
E: Unable to locate package elasticsearch-curator
Reading package lists...
Building dependency tree...
Reading state information...
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
exim4-base set on hold.
mailutils set on hold.
pcp set on hold.
cockpit-pcp set on hold.
__        __   _                                             _     
\ \      / /__| |__  _   _ ___  ___ _ __    ___ _ __ ___  __| |___ 
 \ \ /\ / / _ \ '_ \| | | / __|/ _ \ '__|  / __| '__/ _ \/ _` / __|
  \ V  V /  __/ |_) | |_| \__ \  __/ |    | (__| | |  __/ (_| \__ \
   \_/\_/ \___|_.__/ \__,_|___/\___|_|     \___|_|  \___|\__,_|___/
                                                                   
Adding password for user webuser

 _   _  ____ ___ _   ___  __   ____          _   _  __ _           _       
| \ | |/ ___|_ _| \ | \ \/ /  / ___|___ _ __| |_(_)/ _(_) ___ __ _| |_ ___ 
|  \| | |  _ | ||  \| |\  /  | |   / _ \ '__| __| | |_| |/ __/ _` | __/ _ \
| |\  | |_| || || |\  |/  \  | |__|  __/ |  | |_| |  _| | (_| (_| | ||  __/
|_| \_|\____|___|_| \_/_/\_\  \____\___|_|   \__|_|_| |_|\___\__,_|\__\___|
                                                                           
Generating a RSA private key
........................................................................................................................+++
.............................................................................................................................................................................+++
writing new private key to '/data/nginx/cert/nginx.key'
-----
 _____                           _                         __ _       
| ____|_  ____ _ _ __ ___  _ __ | | ___    ___ ___  _ __  / _(_) __ _ 
|  _| \ \/ / _` | '_ ` _ \| '_ \| |/ _ \  / __/ _ \| '_ \| |_| |/ _` |
| |___ >  < (_| | | | | | | |_) | |  __/ | (_| (_) | | | |  _| | (_| |
|_____/_/\_\__,_|_| |_| |_| .__/|_|\___|  \___\___/|_| |_|_| |_|\__, |
                          |_|                                   |___/ 

### Example static ip config
### Replace <eth0> with the name of your physical interface name
#
#auto eth0
#iface eth0 inet static
# address 192.168.1.1
# netmask 255.255.255.0
# network 192.168.1.0
# broadcast 192.168.1.255
# gateway 192.168.1.1
# dns-nameservers 192.168.1.1

### Example wireless config without 802.1x
### This configuration was tested with the IntelNUC series
### If problems occur you can try and change wpa-driver to "iwlwifi"
#
#auto wlan0
#iface wlan0 inet dhcp
#   wpa-driver wext
#   wpa-ssid <your_ssid_here_without_brackets>
#   wpa-ap-scan 1
#   wpa-proto RSN
#   wpa-pairwise CCMP
#   wpa-group CCMP
#   wpa-key-mgmt WPA-PSK
#   wpa-psk "<your_password_here_without_brackets>"

 ____ ____  _   _                             _                      __  __ 
/ ___/ ___|| | | |  _ __ ___   __ _ _ __ ___ (_)_ __   __ _    ___  / _|/ _|
\___ \___ \| |_| | | '__/ _ \ / _` | '_ ` _ \| | '_ \ / _` |  / _ \| |_| |_ 
 ___) |__) |  _  | | | | (_) | (_| | | | | | | | | | | (_| | | (_) |  _|  _|
|____/____/|_| |_| |_|  \___/ \__,_|_| |_| |_|_|_| |_|\__, |  \___/|_| |_|  
                                                      |___/                 
UseRoaming no
 ___           _        _ _ _                     _             
|_ _|_ __  ___| |_ __ _| | (_)_ __   __ _   _ __ | | ____ _ ___ 
 | || '_ \/ __| __/ _` | | | | '_ \ / _` | | '_ \| |/ / _` / __|
 | || | | \__ \ || (_| | | | | | | | (_| | | |_) |   < (_| \__ \
|___|_| |_|___/\__\__,_|_|_|_|_| |_|\__, | | .__/|_|\_\__, |___/
                                    |___/  |_|        |___/     
npm WARN deprecated request@2.88.2: request has been deprecated, see https://github.com/request/request/issues/3142
npm WARN deprecated querystring@0.2.0: The querystring API is considered Legacy. new code should use the URLSearchParams API instead.
npm WARN deprecated uuid@3.3.2: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated har-validator@5.1.5: this library is no longer supported
npm WARN deprecated s3signed@0.1.0: This module is no longer maintained. It is provided as is.
/usr/local/bin/elasticdump -> /usr/local/lib/node_modules/elasticdump/bin/elasticdump
/usr/local/bin/multielasticdump -> /usr/local/lib/node_modules/elasticdump/bin/multielasticdump
+ elasticdump@6.94.1
added 111 packages from 194 contributors in 7.209s
Collecting glances[docker]
  Downloading Glances-3.3.0.4-py3-none-any.whl (707 kB)
Collecting yq
  Downloading yq-3.1.0-py3-none-any.whl (17 kB)
Collecting psutil>=5.3.0
  Downloading psutil-5.9.4-cp36-abi3-manylinux_2_12_x86_64.manylinux2010_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl (280 kB)
Collecting packaging
  Downloading packaging-22.0-py3-none-any.whl (42 kB)
Collecting defusedxml
  Downloading defusedxml-0.7.1-py2.py3-none-any.whl (25 kB)
Collecting future
  Downloading future-0.18.2.tar.gz (829 kB)
Collecting python-dateutil; extra == "docker"
  Downloading python_dateutil-2.8.2-py2.py3-none-any.whl (247 kB)
Requirement already satisfied: docker>=2.0.0; extra == "docker" in /usr/lib/python3/dist-packages (from glances[docker]) (4.1.0)
Requirement already satisfied: six; extra == "docker" in /usr/lib/python3/dist-packages (from glances[docker]) (1.14.0)
Requirement already satisfied: PyYAML>=5.3.1 in /usr/lib/python3/dist-packages (from yq) (5.3.1)
Collecting xmltodict>=0.11.0
  Downloading xmltodict-0.13.0-py2.py3-none-any.whl (10.0 kB)
Collecting toml>=0.10.0
  Downloading toml-0.10.2-py2.py3-none-any.whl (16 kB)
Collecting argcomplete>=1.8.1
  Downloading argcomplete-2.0.0-py2.py3-none-any.whl (37 kB)
Building wheels for collected packages: future
  Building wheel for future (setup.py): started
  Building wheel for future (setup.py): finished with status 'done'
  Created wheel for future: filename=future-0.18.2-py3-none-any.whl size=491058 sha256=8319011fd2ae0704313882a56ac5cce4c658e4f4bef516b21b76c5b3395e0e49
  Stored in directory: /root/.cache/pip/wheels/8e/70/28/3d6ccd6e315f65f245da085482a2e1c7d14b90b30f239e2cf4
Successfully built future
Installing collected packages: psutil, packaging, defusedxml, future, python-dateutil, glances, xmltodict, toml, argcomplete, yq
Successfully installed argcomplete-2.0.0 defusedxml-0.7.1 future-0.18.2 glances-3.3.0.4 packaging-22.0 psutil-5.9.4 python-dateutil-2.8.2 toml-0.10.2 xmltodict-0.13.0 yq-3.1.0
  ____ _             _               _____     ____       _   
 / ___| | ___  _ __ (_)_ __   __ _  |_   _|   |  _ \ ___ | |_ 
| |   | |/ _ \| '_ \| | '_ \ / _` |   | |_____| |_) / _ \| __|
| |___| | (_) | | | | | | | | (_| |   | |_____|  __/ (_) | |_ 
 \____|_|\___/|_| |_|_|_| |_|\__, |   |_|     |_|   \___/ \__|
                             |___/                            
Cloning into '/opt/tpot'...
  ____                _                                         
 / ___|_ __ ___  __ _| |_ ___    __ _ _ __ ___  _   _ _ __  ___ 
| |   | '__/ _ \/ _` | __/ _ \  / _` | '__/ _ \| | | | '_ \/ __|
| |___| | |  __/ (_| | ||  __/ | (_| | | | (_) | |_| | |_) \__ \
 \____|_|  \___|\__,_|\__\___|  \__, |_|  \___/ \__,_| .__/|___/
                                |___/                |_|        
Adding group `tpot' (GID 2000) ...
Done.
Adding group `tpotlogs' (GID 1001) ...
Done.
  ____                _                             
 / ___|_ __ ___  __ _| |_ ___   _   _ ___  ___ _ __ 
| |   | '__/ _ \/ _` | __/ _ \ | | | / __|/ _ \ '__|
| |___| | |  __/ (_| | ||  __/ | |_| \__ \  __/ |   
 \____|_|  \___|\__,_|\__\___|  \__,_|___/\___|_|   
                                                    
Adding system user `tpot' (UID 2000) ...
Adding new user `tpot' (UID 2000) with group `tpot' ...
Not creating home directory `/home/tpot'.
 ____       _     _               _                              
/ ___|  ___| |_  | |__   ___  ___| |_ _ __   __ _ _ __ ___   ___ 
\___ \ / _ \ __| | '_ \ / _ \/ __| __| '_ \ / _` | '_ ` _ \ / _ \
 ___) |  __/ |_  | | | | (_) \__ \ |_| | | | (_| | | | | | |  __/
|____/ \___|\__| |_| |_|\___/|___/\__|_| |_|\__,_|_| |_| |_|\___|
                                                                 
    _       _  _           _                      _       
   / \   __| |(_)_   _ ___| |_   _ __   ___  _ __| |_ ___ 
  / _ \ / _` || | | | / __| __| | '_ \ / _ \| '__| __/ __|
 / ___ \ (_| || | |_| \__ \ |_  | |_) | (_) | |  | |_\__ \
/_/   \_\__,_|/ |\__,_|___/\__| | .__/ \___/|_|   \__|___/
            |__/                |_|                       
[Socket]
ListenStream=
ListenStream=64294


Port 64295
Match Group tpotlogs
        PermitOpen 127.0.0.1:64305
        ForceCommand /usr/bin/false

 ____ _____  _    _   _ ____    _    ____  ____  
/ ___|_   _|/ \  | \ | |  _ \  / \  |  _ \|  _ \ 
\___ \ | | / _ \ |  \| | | | |/ _ \ | |_) | | | |
 ___) || |/ ___ \| |\  | |_| / ___ \|  _ <| |_| |
|____/ |_/_/   \_\_| \_|____/_/   \_\_| \_\____/ 
                                                 
 ____        _ _   _                                 
|  _ \ _   _| | | (_)_ __ ___   __ _  __ _  ___  ___ 
| |_) | | | | | | | | '_ ` _ \ / _` |/ _` |/ _ \/ __|
|  __/| |_| | | | | | | | | | | (_| | (_| |  __/\__ \
|_|    \__,_|_|_| |_|_| |_| |_|\__,_|\__, |\___||___/
                                     |___/           
2204: Pulling from dtagdevsec/adbhoney
213ec9aee27d: Pulling fs layer
dc68629fbcdb: Pulling fs layer
e7e2668d8d3e: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Waiting
dc68629fbcdb: Verifying Checksum
dc68629fbcdb: Download complete
213ec9aee27d: Verifying Checksum
213ec9aee27d: Download complete
213ec9aee27d: Pull complete
dc68629fbcdb: Pull complete
4f4fb700ef54: Download complete
e7e2668d8d3e: Verifying Checksum
e7e2668d8d3e: Download complete
e7e2668d8d3e: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:48a66583fcebf3e77e8ebb7d7b10c58dfbce0d56b82a5b02128c2fe744d1a261
Status: Downloaded newer image for dtagdevsec/adbhoney:2204
docker.io/dtagdevsec/adbhoney:2204
2204: Pulling from dtagdevsec/ciscoasa
213ec9aee27d: Already exists
a96cd8de2cfd: Pulling fs layer
10d79b25fb50: Pulling fs layer
d7d635bc84b5: Pulling fs layer
d7d635bc84b5: Verifying Checksum
d7d635bc84b5: Download complete
a96cd8de2cfd: Verifying Checksum
a96cd8de2cfd: Download complete
a96cd8de2cfd: Pull complete
10d79b25fb50: Verifying Checksum
10d79b25fb50: Download complete
10d79b25fb50: Pull complete
d7d635bc84b5: Pull complete
Digest: sha256:65404eb5032f582572f968a23f83176333cc37b068370c919f18a7fe88a31754
Status: Downloaded newer image for dtagdevsec/ciscoasa:2204
docker.io/dtagdevsec/ciscoasa:2204
2204: Pulling from dtagdevsec/citrixhoneypot
213ec9aee27d: Already exists
513876a4792b: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
513876a4792b: Verifying Checksum
513876a4792b: Download complete
513876a4792b: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:c5aedff466246c1041e3bfa0edc58b72a0fc5588c5e4b5be20cd015275bb8c02
Status: Downloaded newer image for dtagdevsec/citrixhoneypot:2204
docker.io/dtagdevsec/citrixhoneypot:2204
2204: Pulling from dtagdevsec/conpot
213ec9aee27d: Already exists
06f9af0f67bc: Pulling fs layer
e58a5cf8fe56: Pulling fs layer
06f9af0f67bc: Verifying Checksum
06f9af0f67bc: Download complete
06f9af0f67bc: Pull complete
e58a5cf8fe56: Verifying Checksum
e58a5cf8fe56: Download complete
e58a5cf8fe56: Pull complete
Digest: sha256:b7e72e27889e31e294dd601fcf81f2e9674118d1ff18e082509ccdc533a57f29
Status: Downloaded newer image for dtagdevsec/conpot:2204
docker.io/dtagdevsec/conpot:2204
2204: Pulling from dtagdevsec/cowrie
213ec9aee27d: Already exists
1dd82819c4e3: Pulling fs layer
180ed4eb9684: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
1dd82819c4e3: Verifying Checksum
1dd82819c4e3: Download complete
1dd82819c4e3: Pull complete
180ed4eb9684: Verifying Checksum
180ed4eb9684: Download complete
180ed4eb9684: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:04ceced6bd8dadc51d59b6185a18e6020fb886a5f2493c88c92eeaa6096e8615
Status: Downloaded newer image for dtagdevsec/cowrie:2204
docker.io/dtagdevsec/cowrie:2204
2204: Pulling from dtagdevsec/ddospot
213ec9aee27d: Already exists
da4a6cecaa55: Pulling fs layer
e62aefd178d7: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
da4a6cecaa55: Verifying Checksum
da4a6cecaa55: Download complete
da4a6cecaa55: Pull complete
e62aefd178d7: Verifying Checksum
e62aefd178d7: Download complete
e62aefd178d7: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:4025e6fcb79c7e21ff29f3f7785b0ecd69aacd3b3ee30ee54d795274c7a50ae6
Status: Downloaded newer image for dtagdevsec/ddospot:2204
docker.io/dtagdevsec/ddospot:2204
2204: Pulling from dtagdevsec/dicompot
213ec9aee27d: Already exists
cce8b84f32c1: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
cce8b84f32c1: Verifying Checksum
cce8b84f32c1: Download complete
cce8b84f32c1: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:39faba4bc25195a473a7c90ab024c1ab85d8aafee98695ce8d247489f611d564
Status: Downloaded newer image for dtagdevsec/dicompot:2204
docker.io/dtagdevsec/dicompot:2204
2204: Pulling from dtagdevsec/dionaea
e96e057aae67: Pulling fs layer
70a752818fee: Pulling fs layer
9b09f65ed705: Pulling fs layer
70a752818fee: Download complete
e96e057aae67: Verifying Checksum
e96e057aae67: Download complete
e96e057aae67: Pull complete
70a752818fee: Pull complete
9b09f65ed705: Verifying Checksum
9b09f65ed705: Download complete
9b09f65ed705: Pull complete
Digest: sha256:2f4a81b0e847ab528cb4cd12660d4f2f1679ff8d6d4339e796a9d16c419442d7
Status: Downloaded newer image for dtagdevsec/dionaea:2204
docker.io/dtagdevsec/dionaea:2204
2204: Pulling from dtagdevsec/elasticpot
213ec9aee27d: Already exists
970b4b5461af: Pulling fs layer
505333c165a3: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
970b4b5461af: Verifying Checksum
970b4b5461af: Download complete
970b4b5461af: Pull complete
505333c165a3: Verifying Checksum
505333c165a3: Download complete
505333c165a3: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:4024068db9b22157d1c1cc36cf0f1a29d30fc29b9d3249c05bb539a7280e7a41
Status: Downloaded newer image for dtagdevsec/elasticpot:2204
docker.io/dtagdevsec/elasticpot:2204
2204: Pulling from dtagdevsec/heralding
9621f1afde84: Pulling fs layer
debdd5e181af: Pulling fs layer
92e74142b7ee: Pulling fs layer
7d9b56728784: Pulling fs layer
7d9b56728784: Waiting
debdd5e181af: Verifying Checksum
debdd5e181af: Download complete
9621f1afde84: Verifying Checksum
9621f1afde84: Download complete
9621f1afde84: Pull complete
debdd5e181af: Pull complete
92e74142b7ee: Verifying Checksum
92e74142b7ee: Download complete
7d9b56728784: Download complete
92e74142b7ee: Pull complete
7d9b56728784: Pull complete
Digest: sha256:529c8929668aa146b77a5647428def9b9a116bbbf6e3dd389a0b3889b9946529
Status: Downloaded newer image for dtagdevsec/heralding:2204
docker.io/dtagdevsec/heralding:2204
2204: Pulling from dtagdevsec/honeytrap
e96e057aae67: Already exists
38f79b2e9d52: Pulling fs layer
7bb09880aaf0: Pulling fs layer
38f79b2e9d52: Verifying Checksum
38f79b2e9d52: Download complete
38f79b2e9d52: Pull complete
7bb09880aaf0: Download complete
7bb09880aaf0: Pull complete
Digest: sha256:63f1a25887c20bd6703e1b27888ee972bb8251a0e82629eac84d098ec6605a10
Status: Downloaded newer image for dtagdevsec/honeytrap:2204
docker.io/dtagdevsec/honeytrap:2204
2204: Pulling from dtagdevsec/ipphoney
213ec9aee27d: Already exists
6a8954da7409: Pulling fs layer
9e744572128f: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
6a8954da7409: Verifying Checksum
6a8954da7409: Download complete
6a8954da7409: Pull complete
9e744572128f: Verifying Checksum
9e744572128f: Download complete
9e744572128f: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:524de36cbbe9de242d7111d6d72cc1d8bfdf23e3a3b789beefec3917054027a5
Status: Downloaded newer image for dtagdevsec/ipphoney:2204
docker.io/dtagdevsec/ipphoney:2204
2204: Pulling from dtagdevsec/mailoney
9621f1afde84: Already exists
11db5404c17b: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
11db5404c17b: Download complete
11db5404c17b: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:42a3a04601c132825c06c7a2f6516e1ba414d94d7188fab6aad4185c422d729e
Status: Downloaded newer image for dtagdevsec/mailoney:2204
docker.io/dtagdevsec/mailoney:2204
2204: Pulling from dtagdevsec/medpot
213ec9aee27d: Already exists
759c88ed9863: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
759c88ed9863: Verifying Checksum
759c88ed9863: Download complete
759c88ed9863: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:b9dca7378e750e78ba2face59f0d181168973182d83fe1443b8cf9347393dd84
Status: Downloaded newer image for dtagdevsec/medpot:2204
docker.io/dtagdevsec/medpot:2204
2204: Pulling from dtagdevsec/redishoneypot
213ec9aee27d: Already exists
40ec1c671e5b: Pulling fs layer
140a6319f8cc: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Download complete
40ec1c671e5b: Verifying Checksum
40ec1c671e5b: Download complete
40ec1c671e5b: Pull complete
140a6319f8cc: Verifying Checksum
140a6319f8cc: Download complete
140a6319f8cc: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:1070ada511bc088393409a7dc6b55120b4717647b4f7fd8d5c9d34de310e73ba
Status: Downloaded newer image for dtagdevsec/redishoneypot:2204
docker.io/dtagdevsec/redishoneypot:2204
2204: Pulling from dtagdevsec/sentrypeer
88ecf269dec3: Pulling fs layer
801eed3b315e: Pulling fs layer
88ecf269dec3: Verifying Checksum
88ecf269dec3: Download complete
88ecf269dec3: Pull complete
801eed3b315e: Verifying Checksum
801eed3b315e: Download complete
801eed3b315e: Pull complete
Digest: sha256:c44d1f0d03c22ecbc27406309cad7978befaf98d21ed3188a5dec99c04d4eaf7
Status: Downloaded newer image for dtagdevsec/sentrypeer:2204
docker.io/dtagdevsec/sentrypeer:2204
2204: Pulling from dtagdevsec/redis
9621f1afde84: Already exists
e941b73461cd: Pulling fs layer
3b4b7f645394: Pulling fs layer
e941b73461cd: Download complete
e941b73461cd: Pull complete
3b4b7f645394: Verifying Checksum
3b4b7f645394: Download complete
3b4b7f645394: Pull complete
Digest: sha256:7ffc432719f0b874eb86dc2797cc9ce0c29b5e8571a40899f4234e9d91b2902b
Status: Downloaded newer image for dtagdevsec/redis:2204
docker.io/dtagdevsec/redis:2204
2204: Pulling from dtagdevsec/phpox
9621f1afde84: Already exists
209dac1c5fb7: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
209dac1c5fb7: Verifying Checksum
209dac1c5fb7: Download complete
209dac1c5fb7: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:215d4b3e6e4928958ba2f05643fdffcb48cd24c6f1e015cb59f90b8a2a259091
Status: Downloaded newer image for dtagdevsec/phpox:2204
docker.io/dtagdevsec/phpox:2204
2204: Pulling from dtagdevsec/tanner
9621f1afde84: Already exists
ee0a5554856d: Pulling fs layer
00c745ffe4d7: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Download complete
ee0a5554856d: Download complete
ee0a5554856d: Pull complete
00c745ffe4d7: Verifying Checksum
00c745ffe4d7: Download complete
00c745ffe4d7: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:5d7615ad915a18e3075f7ab799c9ee92ef1ae7566a158266eb4c981ba3700aad
Status: Downloaded newer image for dtagdevsec/tanner:2204
docker.io/dtagdevsec/tanner:2204
2204: Pulling from dtagdevsec/snare
9621f1afde84: Already exists
7b5529a7cbee: Pulling fs layer
8e30654cd833: Pulling fs layer
7b5529a7cbee: Verifying Checksum
7b5529a7cbee: Download complete
7b5529a7cbee: Pull complete
8e30654cd833: Verifying Checksum
8e30654cd833: Download complete
8e30654cd833: Pull complete
Digest: sha256:801b359ca69f3ebe4734e548cb9103a346260f6516e79e1304bddc4c5765a977
Status: Downloaded newer image for dtagdevsec/snare:2204
docker.io/dtagdevsec/snare:2204
2204: Pulling from dtagdevsec/fatt
213ec9aee27d: Already exists
883ee43385d6: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Download complete
883ee43385d6: Verifying Checksum
883ee43385d6: Download complete
883ee43385d6: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:fe4e0f75901401a7c2cecba4dd3b6e6c4dfaa0532d11b7fd8e85c6ae3130ace0
Status: Downloaded newer image for dtagdevsec/fatt:2204
docker.io/dtagdevsec/fatt:2204
2204: Pulling from dtagdevsec/p0f
213ec9aee27d: Already exists
4c7fbf36fd4b: Pulling fs layer
856cfce9580d: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
4c7fbf36fd4b: Verifying Checksum
4c7fbf36fd4b: Download complete
856cfce9580d: Verifying Checksum
856cfce9580d: Download complete
4c7fbf36fd4b: Pull complete
856cfce9580d: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:1bbaf768a26630beb6474859bef1d629fedb6b18f07ff66cf92f0be96c887568
Status: Downloaded newer image for dtagdevsec/p0f:2204
docker.io/dtagdevsec/p0f:2204
2204: Pulling from dtagdevsec/suricata
88ecf269dec3: Already exists
8a1c0097acb6: Pulling fs layer
f76678b8ae46: Pulling fs layer
8a1c0097acb6: Verifying Checksum
8a1c0097acb6: Download complete
8a1c0097acb6: Pull complete
f76678b8ae46: Verifying Checksum
f76678b8ae46: Download complete
f76678b8ae46: Pull complete
Digest: sha256:0599dc25862e4cff4a855bed6fdffd8e9d01241dee2328ae1d91103dcd7d02f6
Status: Downloaded newer image for dtagdevsec/suricata:2204
docker.io/dtagdevsec/suricata:2204
2204: Pulling from dtagdevsec/elasticsearch
e96e057aae67: Already exists
a52c154a9605: Pulling fs layer
e10ecb8a1573: Pulling fs layer
a52c154a9605: Verifying Checksum
a52c154a9605: Download complete
a52c154a9605: Pull complete



e10ecb8a1573: Verifying Checksum
e10ecb8a1573: Download complete
e10ecb8a1573: Pull complete
Digest: sha256:53fc5d54b379cf1b8abbfc4b11ba59511fe60184ee9ab41a70bc700e34115e4c
Status: Downloaded newer image for dtagdevsec/elasticsearch:2204
docker.io/dtagdevsec/elasticsearch:2204
2204: Pulling from dtagdevsec/kibana
e96e057aae67: Already exists
fc5d9a3a8944: Pulling fs layer
7c06bca22048: Pulling fs layer
fc5d9a3a8944: Verifying Checksum
fc5d9a3a8944: Download complete
fc5d9a3a8944: Pull complete
7c06bca22048: Verifying Checksum
7c06bca22048: Download complete
7c06bca22048: Pull complete
Digest: sha256:3e8788bada36d0c58da67bfcb47c3c6abe696760593ba51fac864f4be351304b
Status: Downloaded newer image for dtagdevsec/kibana:2204
docker.io/dtagdevsec/kibana:2204
2204: Pulling from dtagdevsec/logstash
e96e057aae67: Already exists
a5b90e993b58: Pulling fs layer
2c07ef2a7a38: Pulling fs layer
a5b90e993b58: Download complete
a5b90e993b58: Pull complete
2c07ef2a7a38: Verifying Checksum
2c07ef2a7a38: Download complete
2c07ef2a7a38: Pull complete
Digest: sha256:54bba4c471685dfb40d8c13f11d636447a8ed4a1c4c1a92604795723b89612e5
Status: Downloaded newer image for dtagdevsec/logstash:2204
docker.io/dtagdevsec/logstash:2204
2204: Pulling from dtagdevsec/redis
Digest: sha256:7ffc432719f0b874eb86dc2797cc9ce0c29b5e8571a40899f4234e9d91b2902b
Status: Image is up to date for dtagdevsec/redis:2204
docker.io/dtagdevsec/redis:2204
2204: Pulling from dtagdevsec/map
9621f1afde84: Already exists
2dac136270ca: Pulling fs layer
ac416a558392: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
2dac136270ca: Verifying Checksum
2dac136270ca: Download complete
2dac136270ca: Pull complete
ac416a558392: Verifying Checksum
ac416a558392: Download complete
ac416a558392: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:4a4f90aed7835ffe1bcbcc5f7299ead6a0ef3932a54a9701dd773624d48cf13a
Status: Downloaded newer image for dtagdevsec/map:2204
docker.io/dtagdevsec/map:2204
2204: Pulling from dtagdevsec/ewsposter
213ec9aee27d: Already exists
cbbb2ba12c3f: Pulling fs layer
17ebc3188119: Pulling fs layer
cbbb2ba12c3f: Verifying Checksum
cbbb2ba12c3f: Download complete
cbbb2ba12c3f: Pull complete
17ebc3188119: Verifying Checksum
17ebc3188119: Download complete
17ebc3188119: Pull complete
Digest: sha256:414324fd1520975e2c597b51269e51df90d746990a57981e59638eebadead617
Status: Downloaded newer image for dtagdevsec/ewsposter:2204
docker.io/dtagdevsec/ewsposter:2204
2204: Pulling from dtagdevsec/nginx
213ec9aee27d: Already exists
8c956186e570: Pulling fs layer
d88ac8c223a9: Pulling fs layer
8c956186e570: Verifying Checksum
8c956186e570: Download complete
8c956186e570: Pull complete
d88ac8c223a9: Download complete
d88ac8c223a9: Pull complete
Digest: sha256:c4c8d3845afbf3edbc62fae876765a2ff531f22ef902b0a40525014c83cdb557
Status: Downloaded newer image for dtagdevsec/nginx:2204
docker.io/dtagdevsec/nginx:2204
2204: Pulling from dtagdevsec/spiderfoot
213ec9aee27d: Already exists
760951798073: Pulling fs layer
f8794e94106e: Pulling fs layer
4f4fb700ef54: Pulling fs layer
4f4fb700ef54: Verifying Checksum
4f4fb700ef54: Download complete
760951798073: Verifying Checksum
760951798073: Download complete
760951798073: Pull complete
f8794e94106e: Verifying Checksum
f8794e94106e: Download complete
f8794e94106e: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:f9a88c134631db6b35d4a83d5e12f66183b286d980c3488f63dd3b6dafa7b1ae
Status: Downloaded newer image for dtagdevsec/spiderfoot:2204
docker.io/dtagdevsec/spiderfoot:2204
 __  __           _ _  __              _               _        
|  \/  | ___   __| (_)/ _|_   _    ___| |__   ___  ___| | _____ 
| |\/| |/ _ \ / _` | | |_| | | |  / __| '_ \ / _ \/ __| |/ / __|
| |  | | (_) | (_| | |  _| |_| | | (__| | | |  __/ (__|   <\__ \
|_|  |_|\___/ \__,_|_|_|  \__, |  \___|_| |_|\___|\___|_|\_\___/
                          |___/                                 
APT::Periodic::Update-Package-Lists "1";
APT::Periodic::Download-Upgradeable-Packages "0";
APT::Periodic::AutocleanInterval "7";

 _____                    _                         _   _ 
|_   _|_      _____  __ _| | __  ___ _   _ ___  ___| |_| |
  | | \ \ /\ / / _ \/ _` | |/ / / __| | | / __|/ __| __| |
  | |  \ V  V /  __/ (_| |   <  \__ \ |_| \__ \ (__| |_| |
  |_|   \_/\_/ \___|\__,_|_|\_\ |___/\__, |___/\___|\__|_|
                                     |___/                

# Reboot after kernel panic, check via /proc/sys/kernel/panic[_on_oops]
# Set required map count for ELK
kernel.panic = 1
kernel.panic_on_oops = 1
vm.max_map_count = 262144

 ____       _                  __       _ _ ____  _                 
/ ___|  ___| |_ _   _ _ __    / _| __ _(_) |___ \| |__   __ _ _ __  
\___ \ / _ \ __| | | | '_ \  | |_ / _` | | | __) | '_ \ / _` | '_ \ 
 ___) |  __/ |_| |_| | |_) | |  _| (_| | | |/ __/| |_) | (_| | | | |
|____/ \___|\__|\__,_| .__/  |_|  \__,_|_|_|_____|_.__/ \__,_|_| |_|
                     |_|                                            
[DEFAULT]
ignoreip = 127.0.0.1/8
bantime = 3600
findtime = 600
maxretry = 5

[nginx-http-auth]
enabled  = true
filter   = nginx-http-auth
port     = 64297
logpath  = /data/nginx/log/error.log

[pam-generic]
enabled = true
port    = 64294
filter  = pam-generic
logpath = /var/log/auth.log

[sshd]
enabled = true
port    = 64295
filter  = sshd
logpath = /var/log/auth.log

 ____            _                     _    __ _      
/ ___| _   _ ___| |_ ___ _ __ ___   __| |  / _(_)_  __
\___ \| | | / __| __/ _ \ '_ ` _ \ / _` | | |_| \ \/ /
 ___) | |_| \__ \ ||  __/ | | | | | (_| | |  _| |>  < 
|____/ \__, |___/\__\___|_| |_| |_|\__,_| |_| |_/_/\_\
       |___/                                          
[Link]
NamePolicy=kernel database onboard slot path
MACAddressPolicy=none

    _       _     _                         _       _         
   / \   __| | __| |   ___ _ __ ___  _ __  (_) ___ | |__  ___ 
  / _ \ / _` |/ _` |  / __| '__/ _ \| '_ \ | |/ _ \| '_ \/ __|
 / ___ \ (_| | (_| | | (__| | | (_) | | | || | (_) | |_) \__ \
/_/   \_\__,_|\__,_|  \___|_|  \___/|_| |_|/ |\___/|_.__/|___/
                                         |__/                 

# Check if updated images are available and download them
40 2 * * *      root    docker-compose -f /opt/tpot/etc/tpot.yml pull

# Uploaded binaries are not supposed to be downloaded
*/1 * * * *     root    mv --backup=numbered /data/dionaea/roots/ftp/* /data/dionaea/binaries/

# Daily reboot
40 4 * * 1-6      root    systemctl stop tpot && docker stop $(docker ps -aq) && docker rm $(docker ps -aq); reboot

# Check for updated packages every sunday, upgrade and reboot
40 4 * * 0     root    apt-fast autoclean -y && apt-fast autoremove -y && apt-fast update -y && apt-fast upgrade -y && sleep 10 && reboot

 _____ _ _              ___      __       _     _               
|  ___(_) | ___  ___   ( _ )    / _| ___ | | __| | ___ _ __ ___ 
| |_  | | |/ _ \/ __|  / _ \/\ | |_ / _ \| |/ _` |/ _ \ '__/ __|
|  _| | | |  __/\__ \ | (_>  < |  _| (_) | | (_| |  __/ |  \__ \
|_|   |_|_|\___||___/  \___/\/ |_|  \___/|_|\__,_|\___|_|  |___/
                                                                
mkdir: created directory '/data/adbhoney'
mkdir: created directory '/data/adbhoney/downloads'
mkdir: created directory '/data/adbhoney/log'
mkdir: created directory '/data/ciscoasa'
mkdir: created directory '/data/ciscoasa/log'
mkdir: created directory '/data/conpot'
mkdir: created directory '/data/conpot/log'
mkdir: created directory '/data/citrixhoneypot'
mkdir: created directory '/data/citrixhoneypot/logs'
mkdir: created directory '/data/cowrie'
mkdir: created directory '/data/cowrie/downloads'
mkdir: created directory '/data/cowrie/keys'
mkdir: created directory '/data/cowrie/misc'
mkdir: created directory '/data/cowrie/log'
mkdir: created directory '/data/cowrie/log/tty'
mkdir: created directory '/data/ddospot'
mkdir: created directory '/data/ddospot/bl'
mkdir: created directory '/data/ddospot/db'
mkdir: created directory '/data/ddospot/log'
mkdir: created directory '/data/dicompot'
mkdir: created directory '/data/dicompot/images'
mkdir: created directory '/data/dicompot/log'
mkdir: created directory '/data/dionaea'
mkdir: created directory '/data/dionaea/log'
mkdir: created directory '/data/dionaea/bistreams'
mkdir: created directory '/data/dionaea/binaries'
mkdir: created directory '/data/dionaea/rtp'
mkdir: created directory '/data/dionaea/roots'
mkdir: created directory '/data/dionaea/roots/ftp'
mkdir: created directory '/data/dionaea/roots/tftp'
mkdir: created directory '/data/dionaea/roots/www'
mkdir: created directory '/data/dionaea/roots/upnp'
mkdir: created directory '/data/elasticpot'
mkdir: created directory '/data/elasticpot/log'
mkdir: created directory '/data/elk'
mkdir: created directory '/data/elk/data'
mkdir: created directory '/data/elk/log'
mkdir: created directory '/data/endlessh'
mkdir: created directory '/data/endlessh/log'
mkdir: created directory '/data/ews'
mkdir: created directory '/data/ews/conf'
mkdir: created directory '/data/fatt'
mkdir: created directory '/data/fatt/log'
mkdir: created directory '/data/glutton'
mkdir: created directory '/data/glutton/log'
mkdir: created directory '/data/hellpot'
mkdir: created directory '/data/hellpot/log'
mkdir: created directory '/data/heralding'
mkdir: created directory '/data/heralding/log'
mkdir: created directory '/data/honeypots'
mkdir: created directory '/data/honeypots/log'
mkdir: created directory '/data/honeysap'
mkdir: created directory '/data/honeysap/log'
mkdir: created directory '/data/honeytrap'
mkdir: created directory '/data/honeytrap/log'
mkdir: created directory '/data/honeytrap/attacks'
mkdir: created directory '/data/honeytrap/downloads'
mkdir: created directory '/data/ipphoney'
mkdir: created directory '/data/ipphoney/log'
mkdir: created directory '/data/log4pot'
mkdir: created directory '/data/log4pot/log'
mkdir: created directory '/data/log4pot/payloads'
mkdir: created directory '/data/mailoney'
mkdir: created directory '/data/mailoney/log'
mkdir: created directory '/data/medpot'
mkdir: created directory '/data/medpot/log'
mkdir: created directory '/data/nginx/log'
mkdir: created directory '/data/nginx/heimdall'
mkdir: created directory '/data/p0f'
mkdir: created directory '/data/p0f/log'
mkdir: created directory '/data/redishoneypot'
mkdir: created directory '/data/redishoneypot/log'
mkdir: created directory '/data/sentrypeer'
mkdir: created directory '/data/sentrypeer/log'
mkdir: created directory '/data/spiderfoot'
mkdir: created directory '/data/suricata'
mkdir: created directory '/data/suricata/log'
mkdir: created directory '/data/tanner'
mkdir: created directory '/data/tanner/log'
mkdir: created directory '/data/tanner/files'
mkdir: created directory '/home/tsec'
mkdir: created directory '/home/tsec/.ssh/'
  ____                                     __ _           
 / ___|___  _ __  _   _    ___ ___  _ __  / _(_) __ _ ___ 
| |   / _ \| '_ \| | | |  / __/ _ \| '_ \| |_| |/ _` / __|
| |__| (_) | |_) | |_| | | (_| (_) | | | |  _| | (_| \__ \
 \____\___/| .__/ \__, |  \___\___/|_| |_|_| |_|\__, |___/
           |_|    |___/                         |___/     
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/_state/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/_state/state-9.st
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym_8_Lucene90_0.dvd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_k_Lucene90_0.dvm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4z0.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yv.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.nvm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.kdd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym_8_Lucene90_0.dvm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yv.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/write.lock
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yv.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/segments_m
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.nvd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.fdt
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yw.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_k_Lucene90_0.dvd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yy.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.tim
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.fdm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yn.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.fnm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.doc
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yy.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yy.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4z0.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.dvd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.dvm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.kdi
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_k.fnm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym_8.fnm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yw.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4ym.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.tmd
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.fdx
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.pos
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yn.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj_Lucene90_0.tip
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.si
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yw.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4vj.kdm
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4yn.cfs
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/index/_4z0.cfe
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/_state/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/_state/state-2.st
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/_state/retention-leases-783.st
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/translog/
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/translog/translog-22.tlog
data/elk/data/indices/3eIMUpV6RJa1UVrT-HDP-g/0/translog/translog.ckp
Created symlink /etc/systemd/system/multi-user.target.wants/tpot.service → /etc/systemd/system/tpot.service.
 ____                     _         _                 
|  _ \ ___ _ __ _ __ ___ (_)___ ___(_) ___  _ __  ___ 
| |_) / _ \ '__| '_ ` _ \| / __/ __| |/ _ \| '_ \/ __|
|  __/  __/ |  | | | | | | \__ \__ \ | (_) | | | \__ \
|_|   \___|_|  |_| |_| |_|_|___/___/_|\___/|_| |_|___/
                                                      
  ___        _   _                 
 / _ \ _ __ | |_(_) ___  _ __  ___ 
| | | | '_ \| __| |/ _ \| '_ \/ __|
| |_| | |_) | |_| | (_) | | | \__ \
 \___/| .__/ \__|_|\___/|_| |_|___/
      |_|                          
Sourcing file `/etc/default/grub'
Sourcing file `/etc/default/grub.d/50-cloudimg-settings.cfg'
Sourcing file `/etc/default/grub.d/init-select.cfg'
Generating grub configuration file ...
Found linux image: /boot/vmlinuz-5.4.0-135-generic
Found initrd image: /boot/initrd.img-5.4.0-135-generic
Found linux image: /boot/vmlinuz-5.4.0-124-generic
Found initrd image: /boot/initrd.img-5.4.0-124-generic
done
 ____       _                                           _      
/ ___|  ___| |_ _   _ _ __     ___ ___  _ __  ___  ___ | | ___ 
\___ \ / _ \ __| | | | '_ \   / __/ _ \| '_ \/ __|/ _ \| |/ _ \
 ___) |  __/ |_| |_| | |_) | | (_| (_) | | | \__ \ (_) | |  __/
|____/ \___|\__|\__,_| .__/   \___\___/|_| |_|___/\___/|_|\___|
                     |_|                                       
update-initramfs: Generating /boot/initrd.img-5.4.0-135-generic
 ____       _                                                 _   
/ ___|  ___| |_ _   _ _ __    _ __  _ __ ___  _ __ ___  _ __ | |_ 
\___ \ / _ \ __| | | | '_ \  | '_ \| '__/ _ \| '_ ` _ \| '_ \| __|
 ___) |  __/ |_| |_| | |_) | | |_) | | | (_) | | | | | | |_) | |_ 
|____/ \___|\__|\__,_| .__/  | .__/|_|  \___/|_| |_| |_| .__/ \__|
                     |_|     |_|                       |_|        
[[ $- == *i* ]] || return
PS1="\[\033[38;5;8m\][\[$(tput sgr0)\]\[\033[38;5;1m\]\u\[$(tput sgr0)\]\[\033[38;5;6m\]@\[$(tput sgr0)\]\[\033[38;5;4m\]\h\[$(tput sgr0)\]\[\033[38;5;6m\]:\[$(tput sgr0)\]\[\033[38;5;5m\]\w\[$(tput sgr0)\]\[\033[38;5;8m\]]\[$(tput sgr0)\]\[\033[38;5;1m\]\\$\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
export LS_OPTIONS='--color=auto'
eval "`dircolors`"
alias ls='ls $LS_OPTIONS'
alias ll='ls $LS_OPTIONS -l'
alias l='ls $LS_OPTIONS -lA'
PATH="$PATH:/opt/tpot/bin"
[[ $- == *i* ]] || return
PS1="\[\033[38;5;8m\][\[$(tput sgr0)\]\[\033[38;5;2m\]\u\[$(tput sgr0)\]\[\033[38;5;6m\]@\[$(tput sgr0)\]\[\033[38;5;4m\]\h\[$(tput sgr0)\]\[\033[38;5;6m\]:\[$(tput sgr0)\]\[\033[38;5;5m\]\w\[$(tput sgr0)\]\[\033[38;5;8m\]]\[$(tput sgr0)\]\[\033[38;5;2m\]\\$\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
PATH="$PATH:/opt/tpot/bin"
[[ $- == *i* ]] || return
PS1="\[\033[38;5;8m\][\[$(tput sgr0)\]\[\033[38;5;2m\]\u\[$(tput sgr0)\]\[\033[38;5;6m\]@\[$(tput sgr0)\]\[\033[38;5;4m\]\h\[$(tput sgr0)\]\[\033[38;5;6m\]:\[$(tput sgr0)\]\[\033[38;5;5m\]\w\[$(tput sgr0)\]\[\033[38;5;8m\]]\[$(tput sgr0)\]\[\033[38;5;2m\]\\$\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
PATH="$PATH:/opt/tpot/bin"
 _   _           _       _         ___ ____  
| | | |_ __   __| | __ _| |_ ___  |_ _|  _ \ 
| | | | '_ \ / _` |/ _` | __/ _ \  | || |_) |
| |_| | |_) | (_| | (_| | ||  __/  | ||  __/ 
 \___/| .__/ \__,_|\__,_|\__\___| |___|_|    
      |_|                                    
Trying: dig +short myip.opendns.com @resolver3.opendns.com
[MAIN]
ip = 129.114.110.110
HONEY_UUID=


1c40b3d2-78ab-4874-8ba2-1efe4b7baa34
838D-0F6D
MY_EXTIP=129.114.110.110
MY_EXTIP_LAT=32.7157
MY_EXTIP_LONG=-117.1647
MY_INTIP=10.20.4.131
MY_HOSTNAME=marinecandelabra
  ____ _                                
 / ___| | ___  __ _ _ __    _   _ _ __  
| |   | |/ _ \/ _` | '_ \  | | | | '_ \ 
| |___| |  __/ (_| | | | | | |_| | |_) |
 \____|_|\___|\__,_|_| |_|  \__,_| .__/ 
                                 |_|    
Reading package lists...
Building dependency tree...
Reading state information...
Reading package lists...
Building dependency tree...
Reading state information...
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Done. Please reboot.
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# 
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# 
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# 
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# ssh -p 64295 root@129.114.110.110
ssh: connect to host 129.114.110.110 port 64295: Connection timed out
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# ssh -p 64295 root@129.114.110.110
ssh: connect to host 129.114.110.110 port 64295: Connection timed out
root@386056ec-a426-462e-88a5-664027c5a6d8-node1:/home/ubuntu/tpotce/iso/installer# 

