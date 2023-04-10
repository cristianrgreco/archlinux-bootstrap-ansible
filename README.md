# Prerequisites

Host dependencies:
1. python3
2. ansible-core
3. sshpass

Guest dependencies:
1. python3
2. sshd (and running `systemctl start sshd`)
3. sshd configuration (`PermitRootLogin yes`)
4. internet connectivity (dhcpcd)

# Running

Ensure 3D acceleration is enabled in virt-manager.

```bash
ansible-playbook -i inventory.yaml playbook.yaml --user root --ask-pass
```
