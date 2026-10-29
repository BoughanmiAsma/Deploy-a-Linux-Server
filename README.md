# Deploy-a-Linux-Server 🐧

A comprehensive guide to setting up a secure Ubuntu Linux server, deploying a web service (Nginx), and ensuring secure remote access.

This project outlines the steps involved in creating a virtual machine, configuring the Linux environment, securing access via SSH keys, deploying a service, and testing connectivity.

## Table of Contents 📋

- [Project Description](#project-description)
- [Features](#features) ✨
- [Tech Stack](#tech-stack) 💻
- [Installation](#installation) 🚀
- [Usage](#usage) 💡
- [Project Structure](#project-structure) 📁
- [Contributing](#contributing) 🤝
- [License](#license) 📄
- [Important Links](#important-links) 🔗
- [Footer](#footer) 📝

## Project Description 📝

This repository details the process of deploying a secured Ubuntu Server virtual machine. It covers the entire lifecycle from VM creation to deploying a functional web service (Nginx) and ensuring robust security measures. The project is structured around five core steps:

1.  **Create VM** 🏗️
2.  **Configure Linux** ⚙️
3.  **Secure Access** 🔑
4.  **Deploy Service** 🚀
5.  **Test Connectivity** ✅

It is designed for individuals looking to understand and implement server deployment best practices, focusing on security and reliability.

## Features ✨

-   **Virtual Machine Creation**: Step-by-step guide for setting up an Ubuntu Server VM using Oracle VirtualBox.
-   **Linux Configuration**: Detailed steps for initial OS configuration.
-   **Secure SSH Access**: Implementation of ed25519 SSH key pairs, disabling password and root login, and securing the SSH service.
-   **Web Service Deployment**: Deployment and configuration of the Nginx web server.
-   **Network Security**: Configuration of the Uncomplicated Firewall (UFW) to allow only necessary ports.
-   **Brute-Force Protection**: Setup of Fail2ban for enhanced security against attacks.
-   **Automated Security Updates**: Configuration for automatic security updates.
-   **Problem Solving**: Documented common issues encountered during deployment and their solutions.

## Tech Stack 💻

-   **Operating System**: Ubuntu Server 24.04 LTS
-   **Virtualization**: Oracle VirtualBox
-   **Web Server**: Nginx
-   **Security Tools**: UFW, Fail2ban, SSH (ed25519 keys)
-   **Documentation**: Markdown
-   **Scripts/Frameworks (Implicit)**: Python, TypeScript (mentioned but not directly used in provided code snippets, likely for environment setup or related tools)

## Installation 🚀

This project does not involve direct code installation in the traditional sense. It's a guide for setting up a server environment. The primary requirement is having Oracle VirtualBox installed on a Windows host.

**Prerequisites:**

1.  **Oracle VirtualBox**: Download and install from the [official VirtualBox website](https://www.virtualbox.org/).
2.  **Ubuntu Server 24.04 LTS ISO**: Download the ISO image from the [official Ubuntu website](https://ubuntu.com/download/server).

**Steps:**

Follow the detailed instructions within the `docs/` directory:

-   **Step 1: Create VM** (`docs/01-create-vm.md`)
-   **Step 2: Configure Linux** (`docs/02-configure-linux.md`)
-   **Step 3: Secure Access** (`docs/03-secure-access.md`)
-   **Step 4: Deploy Service** (`docs/04-deploy-service.md`)
-   **Step 5: Test Connectivity** (`docs/05-test-connectivity.md`)

## Usage 💡

This project serves as a practical guide for deploying and securing a Linux server. It's intended to be followed step-by-step to build a functional server environment.

**Real-world Use Cases:**

-   **Hosting a Personal Website**: Deploying Nginx to serve static or dynamic web content.
-   **Setting up a Development Environment**: Creating a controlled server environment for testing applications.
-   **Learning Server Administration**: Understanding fundamental Linux server management and security practices.

**How to Use:**

1.  **Follow the Documentation**: Navigate through the `docs/` directory, starting with `01-create-vm.md`.
2.  **Execute Commands**: The documentation specifies commands to be run on either the Windows client or the Ubuntu VM.
3.  **Generate SSH Keys**: Use the provided steps in `docs/03-secure-access.md` to create and deploy your SSH key pair.
4.  **Deploy Nginx**: Follow `docs/04-deploy-service.md` to install and configure the Nginx web server.
5.  **Test Connectivity**: Verify your setup using the methods described in `docs/05-test-connectivity.md`.

**Example Workflow (SSH Key Authentication):**

On your Windows client:
```bash
# Generate SSH key pair (if you don't have one)
ssh-keygen -t ed25519 -C "your_email@example.com"

# Copy the public key to the server (replace 'asma' and '192.168.1.64')
scp ~/.ssh/id_ed25519.pub asma@192.168.1.64:/home/asma/.ssh/authorized_keys

# Connect to the server using the key
ssh asma@192.168.1.64
```

**Example Workflow (Accessing Nginx):**

Open your web browser on the Windows host and navigate to:
```
http://192.168.1.64
```
(Replace `192.168.1.64` with your server's IP address).

## Project Structure 📁

```
Deploy-a-Linux-Server/
├── linux-server-deployment/
│   ├── docs/
│   │   ├── 01-create-vm.md
│   │   ├── 02-configure-linux.md
│   │   ├── 03-secure-access.md
│   │   ├── 04-deploy-service.md
│   │   ├── 05-test-connectivity.md
│   │   └── ssh-ssl-openssl-concepts.pdf
│   ├── screenshots/
│   │   ├── enable-nginx-service.png
│   │   ├── gensshkeys.png
│   │   ├── install-pub-key.png
│   │   ├── simple-login-with-passwors.webp
│   │   ├── scp-pub-key-into-server.png
│   │   ├── test-connectivity.png
│   │   ├── test-service-nginx.png
│   │   ├── ubuntu-VM-configuration.png
│   │   └── deploy-nginx-service.png
│   ├── ufw-rules.txt
│   └── README.md
└── README.md
```

## Contributing 🤝

Contributions are welcome! If you have suggestions for improvements, bug fixes, or new features, please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature or fix (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

Please ensure your contributions align with the project's goals of clear, secure, and effective server deployment.

## License 📄

This project is not specified with a license. Please refer to the repository owner for licensing details.

## Important Links 🔗

-   **Repository**: [Deploy-a-Linux-Server](https://github.com/BoughanmiAsma/Deploy-a-Linux-Server)
-   **Author**: [Asma Boughanmi](https://github.com/BoughanmiAsma)

## Footer 📝

<p align="center">
  <a href="https://github.com/BoughanmiAsma/Deploy-a-Linux-Server" target="_blank">
    <img src="https://img.shields.io/github/stars/BoughanmiAsma/Deploy-a-Linux-Server?style=social" alt="GitHub Stars"></a>
  <a href="https://github.com/BoughanmiAsma/Deploy-a-Linux-Server/fork" target="_blank">
    <img src="https://img.shields.io/github/forks/BoughanmiAsma/Deploy-a-Linux-Server?style=social" alt="GitHub Forks"></a>
  <a href="https://github.com/BoughanmiAsma/Deploy-a-Linux-Server/issues" target="_blank">
    <img src="https://img.shields.io/github/issues/BoughanmiAsma/Deploy-a-Linux-Server?style=social" alt="GitHub Issues"></a>
</p>

Made with ❤️ by [Asma Boughanmi](https://github.com/BoughanmiAsma)

© 2023 [Deploy-a-Linux-Server]. All rights reserved.


---
**<p align="center">Generated by [ReadmeCodeGen](https://www.readmecodegen.com/)</p>**