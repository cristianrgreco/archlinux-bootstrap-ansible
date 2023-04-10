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

1. Create the VM with 3D acceleration enabled.
2. Boot the archlinux VM from the live CD.
3. Run `ip address show` and add the IP address into `inventory.yaml`.

```bash
ansible-playbook -i inventory.yaml archlinux-vm-bootstrap.yaml --user root --ask-pass
```

4. If the VM reboots into the live CD, remove the media and reboot.

You should boot into a VM that looks like this:

![preview.png](preview.png)
