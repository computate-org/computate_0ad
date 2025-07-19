
# Install the prerequisite applications

```bash
sudo subscription-manager repos --enable codeready-builder-for-rhel-9-$(arch)-rpms
sudo dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm
sudo crb enable
```

- https://github.com/computate-org/computate_wxwidgets
- https://github.com/computate-org/computate_libsodium
- https://github.com/computate-org/computate_gloox

```bash

install -d ~/.ansible/roles/computate.computate_wxwidgets
git clone https://github.com/computate-org/computate_wxwidgets.git ~/.ansible/roles/computate.computate_wxwidgets/
cd ~/.ansible/roles/computate.computate_wxwidgets/
ansible-playbook install.yml

install -d ~/.ansible/roles/computate.computate_enet
git clone https://github.com/computate-org/computate_enet.git ~/.ansible/roles/computate.computate_enet/
cd ~/.ansible/roles/computate.computate_enet/
ansible-playbook install.yml

install -d ~/.ansible/roles/computate.computate_gloox
git clone https://github.com/computate-org/computate_gloox.git ~/.ansible/roles/computate.computate_gloox/
cd ~/.ansible/roles/computate.computate_gloox/
ansible-playbook install.yml
```

# Install the 0ad ansible role

```bash
# Create a directory for the ansible role. 
install -d ~/.ansible/roles/computate.computate_0ad

# Clone the 0ad ansible role. 
git clone git@github.com:computate-org/computate_0ad.git ~/.ansible/roles/computate.computate_0ad

# Change into the 0ad ansible role directory. 
cd ~/.ansible/roles/computate.computate_0ad
```

# Run the 0ad ansible playbook to install 0ad locally. 

```bash
ansible-playbook install.yml
```

# Set up firewall on each computer

```bash

# For example on your computer
sudo firewall-cmd --add-port=20595/udp --zone=trusted --permanent
sudo firewall-cmd --add-port=20595/udp --zone=trusted
sudo firewall-cmd --add-source 192.168.86.190/24 --zone trusted
sudo firewall-cmd --add-source 192.168.86.190/24 --zone trusted --permanent

# For example on another computer
sudo firewall-cmd --add-port=20595/udp --zone=trusted --permanent
sudo firewall-cmd --add-port=20595/udp --zone=trusted
sudo firewall-cmd --add-source 192.168.86.37/24 --zone trusted
sudo firewall-cmd --add-source 192.168.86.37/24 --zone trusted --permanent
```
