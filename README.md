# SetupUbuntu
Ansible playbook for installing my dev environment  
Current OS Ubuntu 22.04

# Step 1 - Install ansible
``
sudo apt-add-repository ppa:ansible/ansible
``  
``
sudo apt update
``  
``
sudo apt install ansible
``    
``
ansible-galaxy collection install community.general
``  

# Step 2 - Run ansible playbook from repo
Set your username to install_user var  
``
ansible-playbook setup-ubuntu.yml --ask-become-pass
``

# Step 3 - Manual finalization

#### Switch to zsh
ansible for this is a bit hacky so avoiding it

``
chsh -s $(which zsh)
``

Re-Login

Add some aliases
```bash
echo 'alias copilot="gh copilot"' >> ~/.zshrc && source ~/.zshrc
echo 'alias gcs="gh copilot suggest"' >> ~/.zshrc && source ~/.zshrc
echo 'alias gce="gh copilot explain"' >> ~/.zshrc && source ~/.zshrc
```

Download latest Dockstation from https://dockstation.io/ and install it.  
``
sudo dpkg -i dockstation*.deb
``  
Since that will probably error out use  
``
sudo apt-get install -f
``  