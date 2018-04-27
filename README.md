# cupcake

cupcake is a Linux Distribution based on Arch Linux that sets out to accomplish a few goals.

This distribution is currently in the planning phase. Everything is being planned out before actually being setup (hence the stubs).

* Custom package manager. Pacman is fantastic for the purposes of Arch Linux (consider looking into it if you haven't, it's got a lot of great functionality, and the way Arch does packaging is absolutely beautiful as well), but cupcake aims to have a more user-based installation.

* Cleaner root file system. The normal file system hierarchy of Arch Linux, and by extensions the file system hierarchy standard, is quite dirty in my opinion.

* Use patches and patchsets for the Linux kernel to provide more either responsiveness, processing speed or power, or anything in between.

* Use muslc as opposed to glibc. [muslc](https://www.musl-libc.org)

* Be systemd-free. Systemd is a bit of a cancer in the Linux community, and is too thick for the purposes of cupcake.

* ZSH default shell, with sane defaults.

Note that cupcake is currently, as mentioned previously, in the planning phase. Many things are prone to being changed, removed, and new things to be added. Suggestions are encouraged!

# Table of Contents

* [Plans](https://github.com/Sweets/cupcake#plans)
* [Installation](https://github.com/Sweets/cupcake#installation)
* [Init system](https://github.com/Sweets/cupcake#init-system)
* [Package manager](https://github.com/Sweets/cupcake#package-manager)
* [File system](https://github.com/Sweets/cupcake#file-system)
* [Kernel](https://github.com/Sweets/cupcake#kernel)

# Plans

### Installation

Installation of cupcake should be just as simple as installing Arch Linux.

Users should only need to change their pacman configuration when booted into a live CD (from Arch Linux's mirrorlist to cupake's), and installation of the system will continue as normal (i.e. users will still use `base` to install the base system, but it uses the cupcake base group, rather than Arch's).

### Init system

The init system should be BSD-like, in that `/etc/rc` starts the system itself, and users add things to `/etc/rc.local`. The init script should not handle anything outside of simply starting the system.

This is still being planned out, and is currently the least planned feature.

### Package manager

cupcake aims to provide a more user-oriented installation than other distributions. The package manager, unlike most, will (and should) be ran most often outside of root.

The package manager, ckpkg, has a handful of philosophies:

* Packages that aren't required by the underlying system should be installed to the users home directory, so as not to create bloat on the system itself.

* Users should be able to choose whether they want to build/compile packages themselves, install prebuilt binaries, and/or keep multiple versions of a single package installed.

### File system

* Kernel related directories (`/sys`, `/dev`, `/proc`, etc.) should be a child of `/kernel`.
* Non-home directories (`/usr`, `/tmp`, `/bin`, etc.) should be a child of `/system`.
* The home directory should be more sensible to a new user, and is renamed to `/users` (e.g. `/home/grace` -> `/users/grace`)
* Root's home directory as a child of `/users`
* `/boot` remains untouched.

### Kernel

Patches planned for usage:

* BLD

Kernel planend for usage: Linux Zen
