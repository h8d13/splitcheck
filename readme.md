# splitcheck

Example usage:

```shell
# make edits to PKGBUILD to split packages
# makepkg --printsrcinfo > .SRCINFO
extra-$arch-build -c
./sc.sh OLD.pkg.tar.zst NEW1.pkg.tar.zst [NEW2...]
```

Examples splits:

- [`libguestfs`](https://gitlab.archlinux.org/archlinux/packaging/packages/libguestfs/-/commit/e67304a4ad46f9c769f919acc4394228fcffd559)
- [`avahi`](https://gitlab.archlinux.org/archlinux/packaging/packages/avahi/-/merge_requests/4.diff)
- [`v4l-utils`](https://gitlab.archlinux.org/archlinux/packaging/packages/v4l-utils/-/merge_requests/1.diff)
- [`suil`](https://gitlab.archlinux.org/archlinux/packaging/packages/suil/-/blob/main/PKGBUILD?ref_type=heads)

Some pakcages even deserve a `-docs` split. Which `namcap` detects based on path `/usr/share/doc` not `.html`, `.txt`, `.md` extensions.
