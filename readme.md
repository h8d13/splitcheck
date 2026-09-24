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
- [`suil`](https://gitlab.archlinux.org/archlinux/packaging/packages/suil/-/blob/main/PKGBUILD?ref_type=heads)

https://alpm.archlinux.page/specifications/alpm-sonamev2.7.html

---

This also adheres closer to: https://wiki.archlinux.org/title/Arch_Linux#Simplicity

> Arch Linux official packages do not provide system-wide GUI configuration utilities (i.e. there is neither a GUI installation wizard nor a GUI system configuration tool, and Arch as a distribution does not promote GUI tools for system configuration), encouraging users to perform most system configuration from a command-line shell and a text editor.

Packages including "debug UI tools", examples include splitting `-gtk`, `-qt`, `-somesidecomponent`.

- [`avahi`](https://gitlab.archlinux.org/archlinux/packaging/packages/avahi/-/merge_requests/4.diff)
- [`v4l-utils`](https://gitlab.archlinux.org/archlinux/packaging/packages/v4l-utils/-/merge_requests/1.diff)

> In a similar fashion, Arch ships the configuration files provided by upstream with changes limited to distribution-specific issues like adjusting the system file paths. It does not add automation features such as enabling a service simply because the package was installed. Packages are only split when compelling advantages exist, such as to save disk space in particularly bad cases of waste.

Believe the **same should be true to**: [docs](https://github.com/h8d13/dontreadthedocs) with the Alpine [precedent](https://wiki.alpinelinux.org/wiki/Creating_an_Alpine_package#subpackages) (which I find very neat).
Where a `-docs` convention already exists. I,e: [`wireplumber-docs`](https://gitlab.archlinux.org/archlinux/packaging/packages/wireplumber/-/blob/main/PKGBUILD?ref_type=heads)

---

These obviously take a **bit of work and due process**, but make for a smaller and more "explicit" system.
