# Fix Unable to Compile Kernel Modules

Ensure compiler and libraries are installed

```
$ sudo dnf install kernel-headers kernel-devel elfutils-libelf-devel
$ sudo dnf groupinstall development-tools-and-libraries
```

Compile the Kernel Headers

```
$ sudo ln -s \
  /usr/include/linux/version.h \
  /lib/modules/$(uanme -r)/build/include/linux/version.h
```
