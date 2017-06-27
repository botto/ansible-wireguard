# Wireguard Ansible

Simple role to set up a wireguard server  

## How to use

There are two vars you will be interested in initially:  
`wireguard_root_ip` This is the VPN internal server ip  
`wireguard_clients` List of clients to add to the list  

Each wireguard client looks like:  
`{ public_key: 'fMVHmYgYIl8w6dPnbspiNcXjxNcsYmNUL5hBHbkzEng=', allowed_ip: '10.212.122.10/32', preshared_key: 'pEoSSHnrbk94CJepW8+GGGUThgiJwJHdUszPN/30Xks=' }`


You should end up with:  
```
wiregurd_users:
 - { public_key: 'fMVHmYgYIl8w6dPnbspiNcXjxNcsYmNUL5hBHbkzEng=', allowed_ip: '10.212.122.10/32', preshared_key: 'pEoSSHnrbk94CJepW8+GGGUThgiJwJHdUszPN/30Xks=' }
 - { public_key: '...', allowed_ip: '10.212.122.20/32', preshared_key: '....' }
```

## TODO

[] Inspect existing server config and extract private key
[] Make sure multiple wg instances can be set up i.e.: wg0-server and wg1-server and so on
