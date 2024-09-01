
# Install the prerequisite applications

- https://github.com/computate-org/computate_wxwidgets
- https://github.com/computate-org/computate_enet
- https://github.com/computate-org/computate_miniupnpc
- https://github.com/computate-org/computate_curl
- https://github.com/computate-org/computate_boost
- https://github.com/computate-org/computate_libsodium
- https://github.com/computate-org/computate_gloox

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

Christopher Tate
