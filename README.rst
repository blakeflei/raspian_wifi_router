Raspbian Wifi Router
========================

Ansible configuration to set up a device running Raspbian (Buster) as a wifi router. Developed on a raspberry pi 2b+.

Please update variables (i.e. wifi wpa_pass) such that they are relevant to your network. Default configuration is for an ethernet upstream and wifi downstream, relative to the device.

Currently, firewall config is managed through iptables, as it's included by default in Raspbian Buster. This should probably be changed for a future release.

Installation
------------

Instructions assume a default 'pi' user and sources cloned into the home directory:

- Ensure system is upgraded and followed with a restart::
  
    sudo apt-get update && sudo apt-get upgrade -y && sudo reboot now
  
- Ensure ansible is installed::

    sudo apt-get update && sudo apt-get install ansible

- Clone the repo to the home directory with the commands::

    cd /home/pi

    git clone https://github.com/blakeflei/<repo>.git

- Peruse and update any variables in the ./vars/main.yml::
    cd raspian_wifi_router 
    nano vars/main.yml

- Run ansible playbook::

    ansible-playbook main.yml

- Reboot when completed::
    
    sudo reboot now


Dependencies
~~~~~~~~~~~~
Ansible

References
~~~~~~~~~~
- `https://www.raspberrypi.org/documentation/configuration/wireless/access-point-routed.md <https://www.raspberrypi.org/documentation/configuration/wireless/access-point-routed.md>`__

License
~~~~~~~
BSD 3-Clause License. Please see LICENSE file.
