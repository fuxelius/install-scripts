# Install Ubuntu 18.04 on Dell 3630 Workstation Tower 


# Nsight Install:
 
https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html

0) Install Nvidia CUDA-Kit 10:



1) Test compile nparticle ...

2) Install Java from oracle (For Nvidia Nsight and Profiler)
So turns out that the openjdk-8-jdk package IS NOT what's needed to work with nsight.
You need to install the oracle-java8-installer:

        sudo add-apt-repository ppa:webupd8team/java
        sudo apt update
        sudo apt install oracle-java8-installer


3)
        sudo apt-get install libcanberra-gtk-module


# Useful productivity settings
https://linuxconfig.org/how-to-install-gnome-shell-extensions-on-ubuntu-18-04-bionic-beaver-linux


        $ sudo add-apt-repository universe
        $ sudo apt install gnome-tweak-tool

        (For Hi-Res screens)
        Tweaks->Fonts->Scaling factor: 1.25

        (Virtual Desktops)
        1) Tweaks->Workspaces->Static Workspaces: SET; Number of workspaces-> 6

        2) sudo apt install gnome-shell-extensions

        3) log out and log in again to load gnome-shell-extensions

        4) start Tweaks again

        5) Tweaks->Extensions->Workspace indicator: ON

        6) https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/ (+Add to firefox)

        7) https://extensions.gnome.org/

        8) sudo apt install chrome-gnome-shell

        9) https://extensions.gnome.org/local/  -> search 'workspace grid' (zakkak); install and configure

