# Prerequisites

Host dependencies:
1. python3 (probs already installed)
2. ansible-core (via python)
3. sshpass? (via package manager)

Guest dependencies:
1. Booted into live CD

# How it works

Ansible connects as root via SSH to the guests and bootstraps them.

# Running

1. Create the VM with 3D acceleration enabled.
2. Boot the archlinux VM from the live CD.
3. Set the root password to `root` via `passwd`.
4. Run `ip address show` and add the IP address into `inventory.yaml`.

```bash
ANSIBLE_HOST_KEY_CHECKING=false ansible-playbook -i inventory.yaml archlinux-vm-bootstrap.yaml --user root --ask-pass
```

5. The VM will reboot after bootstrapping. If it reboots into the live CD, power down, remove the live CD, and power on.

Once complete, you should boot into a VM that looks like this:

![preview.png](preview.png)
