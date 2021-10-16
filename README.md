### How to use Ansible ###
If you're not using bash/zsh and Linux based OS good luck lol.

`sudo apt update`

`sudo apt install ansible`

### How Ansible works ###
Ansible is able to do anything a user with SSH access can do. This allows us to avoid repetative tasks when managing several of the same devices.

### Gotcha's ### 
Make sure that `/etc/ansible/ansible.cfg` has all the defaults and settings you want if you are seeing unexpected behavior.