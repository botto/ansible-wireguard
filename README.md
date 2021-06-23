# Wireguard Ansible

Simple role to set up a wireguard server

## Role Variables
    wireguard_root_ip: 10.212.122.1 # VPN address of server
    wireguard_clients: [] # List of clients to add to wireguard config
    wireguard_private_key: "..." # Undefined by default, the role will generate a key on each run


## Example Playbook

    - hosts: webservers
      vars:
        wireguard_private_key: "..."
        wireguard_clients:
          - { public_key: 'fMVHmYgYIl8w6dPnbspiNcXjxNcsYmNUL5hBHbkzEng=', allowed_ip: '10.212.122.10/32', preshared_key: 'pEoSSHnrbk94CJepW8+GGGUThgiJwJHdUszPN/30Xks=' }
          - { public_key: '...', allowed_ip: '10.212.122.20/32', preshared_key: '....' }
      roles:
        - { role: botto.wireguard }

## TODO
- [ ] Inspect existing server config and extract private key
- [ ] Make sure multiple wg instances can be set up i.e.: wg0-server and wg1-server and so on
