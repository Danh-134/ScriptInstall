# Télécharger et installer Visual Studio Code
Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user" -OutFile "VSCodeSetup.exe"
Start-Process -Wait -FilePath ".\VSCodeSetup.exe"
Remove-Item ".\VSCodeSetup.exe" -Force

# Télécharger et installer Git Bash
Invoke-WebRequest -Uri "https://github.com/git-for-windows/git/releases/download/v2.33.0.windows.1/Git-2.33.0-64-bit.exe" -OutFile "GitInstaller.exe"
Start-Process -Wait -FilePath ".\GitInstaller.exe" -ArgumentList "/SILENT"
Remove-Item ".\GitInstaller.exe" -Force

# Télécharger et installer IntelliJ IDEA (Community Edition)
Invoke-WebRequest -Uri "https://download.jetbrains.com/idea/ideaIC-2021.3.2.exe" -OutFile "IntelliJInstaller.exe"
Start-Process -Wait -FilePath ".\IntelliJInstaller.exe" -ArgumentList "/S"
Remove-Item ".\IntelliJInstaller.exe" -Force

# Télécharger et installer Docker Desktop for Windows
Invoke-WebRequest -Uri "https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe" -OutFile "DockerInstaller.exe"
Start-Process -Wait -FilePath ".\DockerInstaller.exe"
Remove-Item ".\DockerInstaller.exe" -Force

# Télécharger et installer Kubernetes (kubectl)
Invoke-WebRequest -Uri "https://dl.k8s.io/release/$(curl.exe -L -s https://dl.k8s.io/release/stable.txt)/bin/windows/amd64/kubectl.exe" -OutFile "kubectl.exe"
Move-Item ".\kubectl.exe" "C:\Windows\System32\kubectl.exe"

# Télécharger et installer Vagrant
Invoke-WebRequest -Uri "https://releases.hashicorp.com/vagrant/2.2.18/vagrant_2.2.18_x86_64.msi" -OutFile "VagrantInstaller.msi"
Start-Process -Wait -FilePath "msiexec.exe" -ArgumentList "/i .\VagrantInstaller.msi /quiet"
Remove-Item ".\VagrantInstaller.msi" -Force

# Télécharger et installer VirtualBox
Invoke-WebRequest -Uri "https://download.virtualbox.org/virtualbox/6.1.26/VirtualBox-6.1.26-145957-Win.exe" -OutFile "VirtualBoxInstaller.exe"
Start-Process -Wait -FilePath ".\VirtualBoxInstaller.exe" -ArgumentList "--silent"
Remove-Item ".\VirtualBoxInstaller.exe" -Force

# Installation de Windows Subsystem for Linux (WSL)
wsl --install

# Télécharger et installer Java 8
Invoke-WebRequest -Uri "https://download.oracle.com/otn-pub/java/jdk/8u311-b10/d7fc238d0cbf4b0bac7f3e17061a5f0d/jre-8u311-windows-x64.exe" -OutFile "Java8Installer.exe"
Start-Process -Wait -FilePath ".\Java8Installer.exe" -ArgumentList "/s"
Remove-Item ".\Java8Installer.exe" -Force

# Télécharger et installer Java 17
Invoke-WebRequest -Uri "https://download.oracle.com/otn-pub/java/jdk/17.0.1+12/9c58b56b70be4955b574be0b134e6205/jre-17.0.1_windows-x64_bin.exe" -OutFile "Java17Installer.exe"
Start-Process -Wait -FilePath ".\Java17Installer.exe" -ArgumentList "/s"
Remove-Item ".\Java17Installer.exe" -Force

# Télécharger et installer DBeaver
Invoke-WebRequest -Uri "https://dbeaver.io/files/dbeaver-ce-latest-x86_64-setup.exe" -OutFile "DBeaverInstaller.exe"
Start-Process -Wait -FilePath ".\DBeaverInstaller.exe"
Remove-Item ".\DBeaverInstaller.exe" -Force

# Télécharger et installer Postman
Invoke-WebRequest -Uri "https://dl.pstmn.io/download/latest/win64" -OutFile "PostmanInstaller.exe"
Start-Process -Wait -FilePath ".\PostmanInstaller.exe"
Remove-Item ".\PostmanInstaller.exe" -Force

# Télécharger et installer Google Chrome
Invoke-WebRequest -Uri "https://dl.google.com/chrome/install/GoogleChromeStandaloneEnterprise64.msi" -OutFile "ChromeInstaller.msi"
Start-Process -Wait -FilePath "msiexec.exe" -ArgumentList "/i .\ChromeInstaller.msi /quiet"
Remove-Item ".\ChromeInstaller.msi" -Force
