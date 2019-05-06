# Ansible-nginx-nfs
Ansible playbook to configure NFS server and client and configure NGINX to serve files from the mount directory.

## Usage
1. Tested against CentOS 7.6.
2. SELinux is set permissive to let nginx access files from NFS mount.
3. Change the values in `inventory.ini` accordingly.
4. Change the mount path from `/dev/sdb1` to the required path in `roles/nfs-server/tasks/main.yml` at `Filesystem for mount drive` and `Set mountpoint` tasks.
5. Make sure ansible can talk to target nodes and sudo without password is configured for the `user` on target node, otherwise add sudo pass to `inventory.ini`.
6. run `ansible-playbook -i inventory.ini master-playbook.yml` from the project root directory.
7. Each role has its own playbook too, which comes handy if there are multiple groups of hosts in `inventory.ini` so that specific roles can be applied on specific groups of hosts.
