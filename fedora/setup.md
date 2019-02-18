# Update The System

```
$ sudo dnf update
```

# Install Required Packages

```
$ sudo dnf install vim git zsh tilix cmake curl pkg-config openssl-devel dconf flatpak snapd
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
 
$ sudo dnf install rpmfusion-free-release-tainted
$ sudo dnf install rpmfusion-nonfree-release-tainted
$ sudo dnf install \*-firmware
```

## Multimedia

```
$ sudo dnf groupupdate multimedia
$ sudo dnf groupupdate sound-and-video
```

# Flatpak

Add the Flathub.org remote:

```
$ flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Install the apps I use:

* VSCode
* Telegram
* Slack
* Dropbox
* Signal
* Discord
* GitKraken

```
$ flatpak install -y flathub com.axosoft.GitKraken
$ flatpak install -y flathub com.discordapp.Discord
$ flatpak install -y flathub com.dropbox.Client
$ flatpak install -y flathub com.slack.Slack
$ flatpak install -y flathub com.visualstudio.code.oss
$ flatpak install -y flathub org.signal.Signal
$ flatpak install -y flathub org.telegram.desktop
```

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

# Multimedia Web Streaming

These notes are older and I usally follow them, but depending on my machine they may not be required:

```
$ sudo dnf install xine-lib\* k3b-extras-freeworld
```

```
$ sudo dnf install gstreamer1-{plugin-crystalhd,ffmpeg,plugins-{good,ugly,bad{,-free,-nonfree,-freeworld,-extras}{,-extras}}} libmpg123 lame-libs --setopt=strict=0
```

```
$ dnf remove gstreamer1-plugins-ugly
```

```
$ sudo dnf install gstreamer1-plugin-mpg123 mpg123-libs
```

```
$ sudo dnf install vlc
```

