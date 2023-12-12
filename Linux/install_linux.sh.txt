#!/bin/bash

# Installation de Visual Studio Code
curl -sSL https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/vscode stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code

# Installation de Git Bash
sudo apt install git

# Installation de IntelliJ IDEA (Community Edition)
sudo snap install intellij-idea-community --classic

# Installation de Docker
sudo apt install docker.io
sudo systemctl enable --now docker

# Installation de Kubernetes (kubectl)
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

# Installation de Vagrant
sudo apt install vagrant

# Installation de VirtualBox
sudo apt install virtualbox

# Installation de WSL (Windows Subsystem for Linux)
wsl --install
