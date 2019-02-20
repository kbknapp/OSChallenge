* No RPM exists for Remarkable Markdown

To Create the RPM manually:

```
$ sudo dnf install rpm-build
$ wget http://download.opensuse.org/repositories/home://zhonghuaren/Fedora_28/src/remarkable-1.87-6.1.src.rpm
$ rpm2cpio | cpio -idmv
$ mkdir -p ~/rpmbuild/{RPMS,SRPMS,SOURCES,SPECS,BUILD}
$ mv *.patch ~/rpmbuild/SOURCES
$ mv Remarkable-1.87.tar.gz ~/rpmbuild/SOURCES
$ mv remarkable.spec ~/rpmbuild/SPECS
$ rpmbuild -ba ~/rpmbuild/SPECS/remarkable.spec
$ sudo dnf install ~/rpmbuild/RPMS/noarch/remarkable-1.87-6.1.noarch.rpm
```
