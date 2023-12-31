# SteamDeckInstallerManager
My code for managing pacman installations to allow easy re-installing after a steam update.

## Install
First, make sure you have root access by creating a password using the following command:
```bash
passwd
```

Then, if you haven't already, run the following command to disable read-only mode for Steam-OS to make pacman installs work:
```bash
sudo steamos-readonly disable
```

Finally, the following command clones the repo to Programs/install_everything, makes install_everything a runnable command and adds all folders within the Programs folder to be on PATH so you can make other scripts easily too.
```bash
mkdir -p /home/deck/Programs/install_everything && git clone https://github.com/aaron777collins/SteamDeckPacmanReInstaller.git /home/deck/Programs/install_everything && sudo chmod +x /home/deck/Programs/install_everything/install_everything && echo -e "\n\n# Adding all folders within Programs to PATH\nfor dir in /home/deck/Programs/*; do\n    if [[ -d \"\$dir\" && \":\$PATH:\" != *\":\$dir:\"* ]]; then\n        PATH=\"\$dir:\$PATH\"\n    fi\ndone" >> ~/.bashrc
```
