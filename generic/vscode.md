# Fix "Visual Studio Code is unable to watch for file changes in this large workspace (error ENOSPC)"

When you see this notification, it indicates that the VS Code file watcher is running out of handles because the workspace is large and contains many files. The current limit can be viewed by running:

```
$ sudo cat /proc/sys/fs/inotify/max_user_watches
```

The limit can be increased to its maximum by editing `/etc/sysctl.conf` and adding this line to the end of the file:

```
fs.inotify.max_user_watches=524288
```

The new value can then be loaded in by running `sudo sysctl -p`. Note that Arch Linux works a little differently, view this page for advice.

While `524288` is the maximum number of files that can be watched, if you're in an environment that is particularly memory constrained, you may wish to lower the number. Each file watch takes up 540 bytes (32-bit) or ~1kB (64-bit), so assuming that all `524288` watches are consumed that results in an upper bound of around 256MB (32-bit) or 512MB (64-bit).
