On ElementaryOS you need to run VMWare Workstation as `root`. I hear it has something to do with gala, but I can't speak intelligently to that.

The solution is edit the `.desktop` file to use `pkexec`.

First, create a new file `/usr/share/polkit-1/actions/com.vmware.Workstation.policy` with the contents:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE policyconfig PUBLIC
 "-//freedesktop//DTD PolicyKit Policy Configuration 1.0//EN"
 "http://www.freedesktop.org/standards/PolicyKit/1/policyconfig.dtd">

<policyconfig>

  <action id="org.freedesktop.policykit.pkexec.run-vmware">
    <description>Run VMWare Workstation</description>
    <message>Authentication is required to run VMWare Workstation</message>
    <defaults>
      <allow_any>no</allow_any>
      <allow_inactive>no</allow_inactive>
      <allow_active>auth_admin_keep</allow_active>
    </defaults>
    <annotate key="org.freedesktop.policykit.exec.path">/usr/bin/vmware</annotate>
    <annotate key="org.freedesktop.policykit.exec.allow_gui">TRUE</annotate>
  </action>

</policyconfig>
```

Next, create a new file (`/usr/bin/vmware-exec`) which will run vmware with `pkexec`. The contents should be:

```
#!/bin/sh
pkexec "/usr/bin/vmware" "$@"
```

Finally, edit the `.desktop` file (`/usr/share/applications/vmware-workstation.desktop`) to run our new `vmware-exec` file (just change the line starting `Exec=`):

```
[Desktop Entry]
Encoding=UTF-8
Name=VMware Workstation
Comment=Run and manage virtual machines
Exec=/usr/bin/vmware-exec %U
Terminal=false
Type=Application
Icon=vmware-workstation
StartupNotify=true
Categories=System;
MimeType=application/x-vmware-vm;application/x-vmware-team;application/x-vmware-enc-vm;x-scheme-handler/vmrc;
```

Now, you can use the GUI icon to launch VMWare and it will ask for root permission. It's not perfect, but at least it gets VMWare working again until this is fixed upstream.

