# cupcake

cupcake is a Linux Distribution based on Arch Linux that sets out to accomplish a few goals.

This distribution is currently in the planning phase. Everything is being planned out before actually being setup (hence the stubs).

* Get rid of Systemd. Systemd is an absolute cancer in the Linux community. It does too much, and is too bloated. There's many articles, pages, lists, etc of why Systemd is bad, refer to one of those.

* Custom package manager. Pacman is fantastic for the purposes of Arch Linux (consider looking into it if you haven't, it's got a lot of great functionality, and the way Arch does packaging is absolutely beautiful as well), but cupcake aims to have a more user-based installation.

* Cleaner root file system. The normal file system hierarchy of Arch Linux, and by extensions the file system hierarchy standard, is quite dirty in my opinion.

# Plans

### Init system

The init system should follow OpenBSD's init system, in that `/etc/rc` starts the system itself, and users add things to `/etc/rc.local`. The init script should not handle anything outside of simply starting the system.

This is still being planned out, and is currently the least planned feature.

### Package manager

cupcake aims to provide a more user-oriented installation than other distributions. The package manager, unlike most, will (and should) be ran most often outside of root.

The package manager, ckpkg, has a handful of philosophies:

* Packages that aren't required by the underlying system should be installed to the users home directory, so as not to create bloat on the system itself.

* Users should be able to choose whether they want to build/compile packages themselves, install prebuilt binaries, and/or keep multiple versions of a package installed (to prevent bitrot).

### File system

* Kernel related directories (`/sys`, `/dev`, `/proc`, etc.) should be a child of `/kernel`.
* Non-home directories (`/usr`, `/tmp`, `/bin`, etc.) should be a child of `/system`.
* The home directory should be more sensible to a new user, and is renamed to `/users` (e.g. `/home/grace` -> `/users/grace`)
* Root's home directory as a child of `/users`
* `/boot` remains untouched.
