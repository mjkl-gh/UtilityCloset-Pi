# UtilityCloset-Pi

A Raspberry Pi Configuration for Internet connectivity

I have had a couple Pis doing random Internet-related duties for years. It's finally time to formalize their configs and make all the DNS/ad-blocking/monitoring stuff encapsulated into one Ansible project.

So that's what this is.

Features


Recommended Pi and OS
You should use a Raspberry Pi zero with usb ethernet adapter or better. 

Setup
Install Ansible. The easiest way (especially on Pi or a Debian system) is via Pip:
(If on Pi/Debian): sudo apt-get install -y python3-pip
(Everywhere): pip3 install ansible
Clone this repository: git clone https://github.com/geerlingguy/internet-pi.git, then enter the repository directory: cd internet-pi.
Install requirements: ansible-galaxy collection install -r requirements.yml (if you see ansible-galaxy: command not found, restart your SSH session or reboot the Pi and try again)
Make copies of the following files and customize them to your liking:
example.inventory.ini to inventory.ini (replace IP address with your Pi's IP, or comment that line and uncomment the connection=local line if you're running it on the Pi you're setting up).
example.config.yml to config.yml
Run the playbook: ansible-playbook main.yml
If running locally on the Pi: You may encounter an error like "Error while fetching server API version". If you do, please either reboot or log out and log back in, then run the playbook again.

Usage


Updating
To upgrade Pi-hole to the latest version, run the following commands:

sudo apt update && sudo apt dist-upgrade

License
MIT

Author
This project was created in 2022 by mjkl-gh

Acknowledgements
This project relies heavily on the work done by:

This project was created in 2021 by Jeff Geerling.