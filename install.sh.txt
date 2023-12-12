#!/bin/bash

# Détection du système d'exploitation
OS=$(uname)
INSTALL_DIR="install"

if [[ "$OS" == "Darwin" ]]; then
    # Sur macOS
    INSTALL_SCRIPT="$INSTALL_DIR/install_mac.scpt"
elif [[ "$OS" == "Linux" ]]; then
    # Sur Linux
    INSTALL_SCRIPT="$INSTALL_DIR/install_linux.sh"
elif [[ "$OS" == "MINGW" ]]; then
    # Sur Windows (Git Bash)
    INSTALL_SCRIPT="$INSTALL_DIR/install_windows.ps1"
else
    echo "Système d'exploitation non pris en charge."
    exit 1
fi

# Exécution du script d'installation approprié
if [ -f "$INSTALL_SCRIPT" ]; then
    chmod +x "$INSTALL_SCRIPT"
    "./$INSTALL_SCRIPT"
else
    echo "Script d'installation non trouvé pour ce système d'exploitation."
    exit 1
fi
