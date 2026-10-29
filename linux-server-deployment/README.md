# Linux Server Deployment

Deployment of a secured Ubuntu Server virtual machine running a web service (Nginx), following five steps:

**Create VM → Configure Linux → Secure Access → Deploy Service → Test Connectivity**

## Environment

| Item | Value |
|---|---|
| Hypervisor | Oracle VirtualBox (Windows host) |
| OS | Ubuntu Server 24.04 LTS (installed from 24.04.4 ISO, updated to 24.04.5) |
| Resources | 4 GB RAM, 2 vCPU, 25 GB virtual disk |
| Network | Bridged adapter (Intel PRO/1000 MT), DHCP address `192.168.1.64` |
| Hostname / user | `ubuntu-server` / `asma` |
| Service | Nginx web server |

## Steps

| # | Step | Documentation | Status |
|---|---|---|---|
| 1 | Create VM | [docs/01-create-vm.md](docs/01-create-vm.md) | ✅ Done |
| 2 | Configure Linux | [docs/02-configure-linux.md](docs/02-configure-linux.md) | ✅ Done |
| 3 | Secure Access | [docs/03-secure-access.md](docs/03-secure-access.md) | ✅ Done |
| 4 | Deploy Service | [docs/04-deploy-service.md](docs/04-deploy-service.md) | ✅ Done |
| 5 | Test Connectivity | [docs/05-test-connectivity.md](docs/05-test-connectivity.md) | ✅ Done |

Theory behind step 3: [SSH keys, SSH vs SSL/TLS vs OpenSSL (PDF)](docs/ssh-ssl-openssl-concepts.pdf)


## Security measures (summary)

- SSH authentication with an **ed25519 key pair** protected by a passphrase
- Password login and root login disabled in SSH
- Firewall (UFW) allowing only the required ports
- Fail2ban against brute-force attempts
- Automatic security updates

## Result

All checks passed: the Nginx page is reachable from the Windows host, SSH accepts only the key, and the firewall blocks everything else.

![Nginx page](screenshots/test-service-nginx.png)

## Problems encountered and fixes

| Problem | Cause | Fix |
|---|---|---|
| VM froze at "Begin: Loading essential drivers" | VirtualBox settings and the Windows hypervisor (Hyper-V) active on the host | Boot order corrected, PAE/NX and KVM paravirtualization set, ISO attached as Live CD, `bcdedit /set hypervisorlaunchtype off`, Memory integrity off (details in [step 1](docs/01-create-vm.md)) |
| `su: Authentication failure` | Root has no password on Ubuntu | Use `sudo` instead of `su` |
| `type ... \| ssh` key copy aborted (`Connection aborted`) | Password prompt fails with a pipe on Windows | Copy with `scp`, then install the key on the server |
| Keyboard in QWERTY on the console | Layout chosen during install | `sudo dpkg-reconfigure keyboard-configuration` |

## Notes

- Private keys are **never** stored in this repository.
- Commands were run on a Windows PowerShell client and on the Ubuntu VM; each document says which.
