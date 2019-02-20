# About

These are the notes on how I set up a system. Some of this is specific to my workflow, but a good bit of it is general enough for others.

Note, this doesn't include things like cloning my dotfiles repos, setting up my terminals the way I like, etc.

# Update The System

```
$ sudo dnf update
```

# Install Required Packages

Most of these (minus `flatpak` and `snapd` are specific to my workflow/job).

```
$ sudo dnf install vim git zsh tilix cmake curl pkg-config openssl-devel dconf flatpak snapd
```

Make sure the basic compiler and tools are installed:

```
$ sudo dnf groupinstall development-tools
```

# Fedora Workstation Repos (if required)

Provides:

* Steam
* nVidia Driver
* Chrome

```
$ sudo dnf install fedora-workstation-repositories
```

The repositories are disabled by default. To enable individual repositories, use the following command:

```
$ sudo dnf config-manager --set-enabled google-chrome
$ sudo dnf config-manager --set-enabled rpmfusion-nonfree-nvidia-driver
$ sudo dnf config-manager --set-enabled rpmfusion-nonfree-steam
```

# RPMFusion Repos

```
$ sudo dnf install \
 https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
 https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
 
$ sudo dnf install rpmfusion-free-release-tainted rpmfusion-nonfree-release-tainted
```

If you need some special firmware (luzbot, b43, etc.):

```
$ sudo dnf install \*-firmware
```

## Multimedia

```
$ sudo dnf groupupdate multimedia
$ sudo dnf groupupdate sound-and-video
```

## Web Streaming

```
$ sudo dnf install xine-lib\* 
```

```
$ sudo dnf install gstreamer1-{plugin-crystalhd,ffmpeg,plugins-{good,ugly,bad{,-free,-nonfree,-freeworld,-extras}{,-extras}}} libmpg123 lame-libs --setopt=strict=0
```

Remove one package which is included in the one liner from above, but we don't actually need.

```
$ dnf remove gstreamer1-plugins-ugly
```

```
$ sudo dnf install gstreamer1-plugin-mpg123 mpg123-libs
```

Install two programs which pull most of the libs the system needs for audio/video:

```
$ sudo dnf install vlc ffmpeg
```

# Add the Fira Code Fonts COPR repository

```
$ sudo dnf copr enable evana/fira-code-fonts
```

Install the fonts

```
$ sudo dnf install fira-code-fonts
```

# Flatpak

Follow [../generic/flatpak.md](../generic/flatpak.md)

# Snap

Link the `/snap` dir that snapd expects and enable the service

```
$ sudo systemctl start snapd
$ sudo systemctl enable snapd
$ sudo ln -s /var/lib/snapd/snap /snap
```

## Install SNAPs

Install the apps I use:

* CLion
* LXD
* Mailspring
* FreeMind

```
$ sudo snap install clion --classic
$ sudo snap install mailspring
$ sudo snap install freemind
```

### LXD (and fix SELinux errors)

```
$ sudo setenforce 0
$ sudo snap install lxd
$ sudo ausearch -m avc -ts recent | audit2allow -M snap # Gather SELinux errors and create a custom 'snap' policy
$ sudo semodule -i snap.pp                              # Install the new snap policy
$ sudo setenforce 1                                     # Set SELinux back to Enforcing Mode
$ sudo usermod -aG lxd myuser                           # Add your user to the 'lxd' group
$ newgrp lxd                                            # quick hack to reload your groups
$ newgrp myuser
$ lxd init                                              # Start using lxd
```

# Keybase

Download RPM and install:

```
$ sudo dnf install https://prerelease.keybase.io/keybase_amd64.rpm
$ run_keybase
```

# Standard Notes

My most used notes program.

Download `.AppImage` from: https://standardnotes.org/extensions?downloaded=linux

## Install

```
$ chmod u+x standard-notes-3.0.4-x86_64.AppImage
$ ./standard-notes-3.0.4-x86_64.AppImage
```

# Buttercup.pw

Password manager.

Download `.RPM` from: https://buttercup.pw/

## Install

```
$ sudo dnf install ./buttercup.rpm
```
