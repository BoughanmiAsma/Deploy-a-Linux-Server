# Screenshots

| File | Step | Shows |
|---|---|---|
| `ubuntu-VM-configuration.png` | 1 | VirtualBox VM configuration |
| `simple-login-with-passwors.webp` | 2 | First login on the VM console |
| `gensshkeys.png` | 3 | Generating the ed25519 key pair |
| `scp-pub-key-into-server.png` | 3 | Copying the public key with `scp` |
| `install-pub-key.png` | 3 | Installing the key in `authorized_keys` |
| `test-connectivity.png` | 3 / 5 | SSH login with the key (passphrase prompt) |
| `deploy-nginx-service.png` | 4 | Enabling and starting Nginx |
| `enable-nginx-service.png` | 4 | Nginx status and firewall rule |
| `test-service-nginx.png` | 5 | Nginx page opened from Windows |

Before committing, check that no screenshot shows passwords, private key contents or tokens.
