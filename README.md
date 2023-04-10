# Prerequisites

Host dependencies:
1. python3 (probs already installed)
2. ansible-core (via python)
3. sshpass (via package manager)

Guest dependencies:
1. python3 (via package manager)
2. sshd (via package manager and running `systemctl start sshd`)
3. sshd configuration (append `PermitRootLogin yes` to `/etc/ssh/sshd_config`)
4. internet connectivity (install `dhcpcd` via package manager and running `systemctl start dhcpcd`)

# How it works

Ansible connects as root via SSH to the guests and bootstraps them.

# Running

Ensure 3D acceleration is enabled in virt-manager.

```bash
ansible-playbook -i inventory.yaml archlinux-vm-bootstrap.yaml --user root --ask-pass
```
