# Rotator Control v1.2 For Linux

> A simple Python application that enables PC remote control of the RCA VH226E antenna rotator when paired with a USB IR interface.
> Tested and working with an Iguanaworks USB IR Transceiver, which is no longer being sold. It **MIGHT** work with an IRDroid USB
> Infrared Transceiver, but I can't confirm this. Purchase one at your **OWN RISK**!

## How to install and run:

sudo apt-get update

sudo apt-get install lirc -y

sudo nano /etc/lirc/lirc_options.conf

> **Modify these two lines as follows:**
> ```text
> driver          = default
> device          = /dev/lirc0
> ```

sudo wget -O /etc/lirc/lircd.conf.d/rca_vh226e_antenna_rotator.conf https://raw.githubusercontent.com/RobVK8FOES/rotator_control_v1.2-linux/refs/heads/main/rca_vh226e_antenna_rotator.conf

sudo systemctl restart lircd

wget https://raw.githubusercontent.com/RobVK8FOES/rotator_control_v1.2-linux/refs/heads/main/rotator_control_v1.2.py

chmod +x rotator_control_v1.2.py

./rotator_control_v1.2.py
