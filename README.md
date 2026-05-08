# Cockpit-ZFS packaged for Debian trixie

This repo takes care of packaing the official zfs modoule from [45drives](https://github.com/45Drives/cockpit-zfs), while also packing the python library `python3-libzfs` from an amazing fork by [asomers](https://github.com/asomers/py-libzfs).

## Important note

The container uses trixie-backports to get the latest libzfs packages. As of today, the package expects `libzfs7linux` instead of `libzfs6linux` found in regular debian sources.

### Rough instalation guide

1. Install ZFS based on the official debian [documentation](https://wiki.debian.org/ZFS#Installation) (make sure to enable backports)
2. Install cockpit based on the official [documentation](https://cockpit-project.org/running#debian) (don't add backports again)
3. Download all three deb files from the latest CI run

4. Install these files in the following order

```bash
sudo apt install ./python3-libzfs_*.deb
sudo apt install ./python3-libzfs-dbgs*.deb
sudo apt install ./cockpit-zfs-custom_*.deb
```
