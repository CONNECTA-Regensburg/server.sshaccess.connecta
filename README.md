# Server SSH Access

This repository automatically distributes "authorized_keys" files to servers.

On a push to this repository, all authorized_keys files are updated on all servers.

## Usage

1. find the key you want to add (e.g. `~/.ssh/id_rsa.pub`)  
   Or create a new one: `ssh-keygen -t ed25519`
   Find your key using `type ~\.ssh\id_ed25519.pub` for windows, `cat ~/.ssh/id_rsa.pub` for linux
3. add the key to the `servername-username` file in this repository (for the server you want to get access to)
4. push the changes to this repository

## Add host

1. add new host to "config" file
2. execute "ssh-keyscan -t ssh-ed25519 [-p port] <hostip or hostname> >> known_hosts" to add the host to known_hosts
3. add host to ".github/workflows/update-all.yml" file
4. push changes to this repository
