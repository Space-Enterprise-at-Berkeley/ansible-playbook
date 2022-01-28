### How to use Ansible ###
If you're not using bash/zsh and Linux based OS good luck lol.

`sudo apt update`

`sudo apt install ansible`

### How Ansible works ###
Ansible is able to do anything a user with SSH access can do. This allows us to avoid repetative tasks when managing several of the same devices.

### Commands to help find device's IP ###
##### nmap #####
This is a utility to use to check properties of your local network.

In your termainl write: `sudo apt install nmap` to install it. (Update your apt package repos if neccesary w/ `sudo apt update`).

To find IP's that are connected to your subnetwork type: `nmap -sn <network_host_ip> ` and give it a second to search for connected devices.

From there if it picks up other devices and you have SSH enabled you can access them.

##### SSH #####
Secure Shell or SSH is a utility to interface with a device over a network. This is perfect for controlling 'headless' devices. That is, devices that do not have a monitor output to interact/monitor it. Instead you can control it through your shell on your local machine and control it through a shell CLI.

For the purposes of our rpi cams, once you have the ip of the cams from the previous step you can SSH into them by typing `ssh pi@<pi_ip_address>`.

It will prompt you for a password: `raspberry`. You typically don't wanna do this with devices you manage in industry or if it connects to the internet but for the purposes of our cameras there's no point to change it from the default for simplicity sake.

##### systemctl #####
Once you're SSH'd into the device you want to configure or monitor, to check whether ustreamer is actually running on the device use the following command: `sudo systemctl status ustreamer.service`.

If ustreamer was setup correctly as a service then you should get a readout of the programs status. It should tell you whether the service running or not, the IP its streaming it to among other things.


### Gotchas ### 
Make sure that `/etc/ansible/ansible.cfg` has all the defaults and settings you want if you are seeing unexpected behavior.ry