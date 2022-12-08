# TPOT-installation-in-FABRIC
This repo contains our initial attempt in installing the T-POT honeypot in a research testbed FABRIC

Clone the T-Pot Git Repository

The first step once we log in is to install git. We will need git to clone the T-Pot repository:

apt-get -y update && apt-get -y install git

Once this finishes, we are ready to clone the T-Pot repo:

git clone https://github.com/telekom-security/tpotce

Access the T-Pot directory:

cd tpotce/

create a configuration file

The T-Pot auto-installer needs certain parameters for the installation. These values can be specified in a configuration file or via the command line. We will use the first option.

# tpot configuration file
# myCONF_TPOT_FLAVOR=[STANDARD, SENSOR, INDUSTRIAL, COLLECTOR, NEXTGEN]
myCONF_TPOT_FLAVOR='STANDARD'
myCONF_WEB_USER='webuser' 
myCONF_WEB_PW='w3b$ecret'

RUN THE T-POT AUTO-INSTALLER

Once the configuration file is created, we are ready to run the /tpotce/install.sh script. This script performs the full installation of the T-Pot framework, including the ELK instances used to ingest and visualize the data.

./install.sh --conf=/root/tpot.conf

The installation process requires none or minimal user interaction and depending on the internet speed it will last around 30 minutes. The installation script will do a full upgrade of the operating system, install all dependencies needed, download and configure the honeypots, install ELK and configure log stash and Kibana. If everything goes well, which it should, you will see a message on the screen asking to reboot the system.

Once the installation finishes, and the system reboots, the normal (not honeypot) SSH will be moved to port 64295. Next time you login you will have to specify the port in the SSH command:

ssh -p 64295 root@xxx.xxx.xxx.xxx

Pre-built Kibana T-Pot dashboards

Now that the installation finished and the server has been reboot, we can access the web interface and the Kibana dashboards. Go to Firefox (Google Chrome may block the access due the use of a self-signed certificate), and access the T-Pot console in port 64297:

https://xxx.xxx.xxx.xxx:64297
