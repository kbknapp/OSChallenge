# `pip install` fails with missing `redhat-hardened-cc1`

If doing `pip install foo` fails with:

```
$ sudo pip install foo
 [...]
gcc: error: /usr/lib/rpm/redhat/redhat-hardened-cc1: No such file or directory
```

Install `redhat-rpm-config`:

```
$ sudo dnf install -y redhat-rpm-config
```

# `pip install` fails missing `Python.h`

If `pip install foo` fails with:

```
$ sudo pip install foo
 [ ... ]
gcc: Python.h no such file or directory
```

Install `python{3,2}-devel`

```
$ sudo dnf install python2-devel
```
