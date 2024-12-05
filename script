#!/bin/bash

# Define directories and files
NODE_DIR="dkn-compute-node"
ENV_FILE=".env"
BACKUP_ENV_FILE=".env.backup"

# Backup the existing .env file if it exists
if [ -f "$NODE_DIR/$ENV_FILE" ]; then
    echo "Backing up existing .env file..."
    cp "$NODE_DIR/$ENV_FILE" "$NODE_DIR/$BACKUP_ENV_FILE"
else
    echo "No existing .env file to backup."
fi

# Determine the system architecture
ARCH=$(uname -m)
echo "Detected architecture: $ARCH"

# Download the appropriate version based on architecture
if [ "$ARCH" = "aarch64" ]; then
    DOWNLOAD_URL="https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-arm64.zip"
elif [ "$ARCH" = "x86_64" ]; then
    DOWNLOAD_URL="https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-amd64.zip"
else
    echo "Unsupported architecture: $ARCH"
    exit 1
fi

# Download the ZIP file
echo "Downloading dkn-compute-node..."
curl -L -o dkn-compute-node.zip "$DOWNLOAD_URL"

# Unzip and move into the directory
echo "Extracting files..."
unzip -o dkn-compute-node.zip -d "$NODE_DIR" && cd "$NODE_DIR" || exit

# Restore the .env file from backup if it exists
if [ -f "$BACKUP_ENV_FILE" ]; then
    echo "Restoring backup .env file..."
    mv "$BACKUP_ENV_FILE" "$ENV_FILE"
fi

# Run the node
echo "Starting dkn-compute-launcher..."
chmod +x ./dkn-compute-launcher
./dkn-compute-launcher
