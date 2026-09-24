# splitcheck

Example usage:

```shell
# make edits to PKGBUILD to split packages
# makepkg --printsrcinfo > .SRCINFO
extra-$arch-build -c
./sc.sh OLD.pkg.tar.zst NEW1.pkg.tar.zst [NEW2...]
```
