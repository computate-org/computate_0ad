
# Install the prerequisite applications

```bash
sudo subscription-manager repos --enable codeready-builder-for-rhel-9-$(arch)-rpms
sudo dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm
sudo crb enable
```

- https://github.com/computate-org/computate_wxwidgets
- https://github.com/computate-org/computate_enet
- https://github.com/computate-org/computate_miniupnpc
- https://github.com/computate-org/computate_curl
- https://github.com/computate-org/computate_libsodium
- https://github.com/computate-org/computate_gloox
- https://github.com/computate-org/computate_miniupnpc

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
