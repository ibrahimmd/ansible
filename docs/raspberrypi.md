# Raspberry Pi

## First-time Setup

### 1. Flash SD card
Use Raspberry Pi Imager with the following configuration:
- OS: Raspberry Pi OS  (64-bit)
- Hostname: set to match inventory (e.g. `pi4`)
- Username: `pi`
- Password: (your choice)
- Enable SSH: password authentication

### 2. Run bootstrap
Connects as `pi` to `pi4`, creates `ibrahim` and `ansible` accounts, removes `pi`.

```bash
ansible-playbook --limit pi4 --user pi --ask-pass --ask-become-pass playbooks/raspberrypi_bootstrap.yml
```

### 3. Run main playbook
```bash
ansible-playbook  playbooks/raspberrypi.yml
```

## Notes
- `ansible_user` is set to `ansible` in `group_vars/all/ansible.yml`
- `ibrahim` SSH key: `~/.ssh/id_ed25519.pub`
- `ansible` SSH key: `~/.ssh/id_ed25519_ansible.pub`
- UID 1000 is reserved for Kubernetes workloads
