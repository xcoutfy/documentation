.. _Developer_manual:

Developer Manual
================

Setting up a server
----------------

Connection to Hamachi

Get the correct version at https://www.vpn.net/linux and install

    wget https://www.vpn.net/installers/logmein-hamachi_2.1.0.203-1_amd64.deb

    sudo dpkg -i logmein-hamachi_2.1.0.203-1_amd64.deb

Login and join a network

    sudo hamachi login

    sudo hamachi do-join network-id

Connection to a OpenVPN

Install OpenVPN

    sudo apt-get install openvpn

Move VPN client key to /etc/openvpn changing the extension

    sudo mv client-config.ovpn /etc/openvpn/client/client-config.conf

Create authentication file auth.txt and change its permitions

    sudo chmod 600 /etc/openvpn/auth.txt

Add below line to the /etc/openvpn/client-config.conf file

    askpass /etc/openvpn/auth.txt

Restart OpenVpn service

    sudo service openvpn restart

Use the openvpn-client@.service like so:

    sudo systemctl start openvpn-client@{client-config}

To start service at boot, run:

    sudo systemctl enable openvpn-client@{client-config}


Setting up a new Orange Pi/Raspberry Pi device
----------------

Format and install Raspberry Pi OS Lite to SD card.

Once OS is installed, first step is to set a new username and password according to the list.

sudo adduser xcoutfypc00

sudo usermod -aG sudo xcoutfypc00

sudo deluser orangepi sudo

Make sure the ssh service is enabled and started:

sudo systemctl enable ssh

sudo systemctl start ssh

Test ssh from other computer.

sudo apt-get update

sudo apt-get upgrade

Install pip

sudo apt install python3-pip

Install openvpn

sudo apt-get install openvpn

sudo apt-get install python3-dev

Install git
sudo apt install git

Generate a ssh key to git clone
ssh-keygen

sudo crontab -e
0 3 * * * /sbin/reboot
0 4 * * 1 /usr/bin/apt update
0 5 * * 1 /usr/bin/apt upgrade -q -y


#. Developer Community
#. Code organisation
#. Development Workflow
#. Coding Standards
   * Syntax convention
   * Golden Rules and Street Fighters
   * Test Driven Development
#. Continuous Integration
#. Quality Assurance and Testing
   * `PEP8 Coding style checker <https://pypi.python.org/pypi/flake8>`_
#. Documentation
   * in code documentation
   * ReadTheCode or public documentation
#. Bug report
#. Licensing
#. Suggested Readings

