# Local Development

## Local Collection Testing

To test local collection changes without committing, symlink your local repos:

```bash
mkdir -p .ansible/local_collections/ansible_collections/ibrahimmd
ln -s /local/path/to/ansible-collection-raspberrypi .ansible/local_collections/ansible_collections/ibrahimmd/raspberrypi
ln -s /local/path/to/ansible-collection-homelab .ansible/local_collections/ansible_collections/ibrahimmd/homelab
ln -s /local/path/to/ansible-collection-xxxx .ansible/local_collections/ansible_collections/ibrahimmd/xxxx
```

Then run the playbook with the local collections path:

```bash
ANSIBLE_COLLECTIONS_PATH=./.ansible/local_collections:./.ansible/collections ansible-playbook --limit pi4.lab playbooks/raspberrypi.yml
```
