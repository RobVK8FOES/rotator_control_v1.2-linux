# rotator_control_v1.2-linux
A simple Python app to enable IR remote control of RCA VH226E antenna rotators

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
