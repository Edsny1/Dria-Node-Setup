# Dria-Node-Setup

https://raw.githubusercontent.com/Edsny1/Dria-Node-Setup/refs/heads/Edsny/script

Prerequisites
Operating System: Ensure you're running Linux (aarch64 or x86_64 architecture).

Packages: Ensure curl and unzip are installed. If not, install them:
```
sudo apt update && sudo apt install -y curl unzip
```
1- Steps to Run the Script

Run the following command to download the script:
```
wget https://raw.githubusercontent.com/Edsny1/Dria-Node-Setup/refs/heads/Edsny/script
```
2-Make the Script Executable: Give the script executable permissions:
```
chmod +x install-script.sh
```
3-Run the Script: Execute the script with:
```
./install-script.sh
```
What the Script Does Backups the .env File: If a .env file exists in the dkn-compute-node directory, it will back it up to .env.backup.

Detects Your System Architecture:

Downloads the appropriate binary (arm64 for ARM or amd64 for x86). Downloads and Unzips the Node:

Fetches the relevant ZIP file from GitHub. Extracts it into the dkn-compute-node directory. Restores the Backup .env File:

Moves the .env.backup file back to .env. Starts the Launcher:

Makes the launcher (dkn-compute-launcher) executable and runs it.


Add Metamask priv key ( fund sepholia eth )
