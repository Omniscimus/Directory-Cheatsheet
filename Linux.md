# Linux Directories

:book: For the complete reference, have a look at the [Filesystem Hierarchy Standard](http://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html) specification.

:exclamation: The most important directories for a typical Linux user are marked **bold**.

## Programs and Scripts
Programs and scripts should always be in the most specific directory possible. For example, consider a system administration program called `feedthebirds`. `feedthebirds` *could* be placed in `/bin`, but if it only makes sense to use the program if you are a logged in user (e.g. when the system birds are initialized), then it is much better at home in `/usr/local/sbin`. :notes::bird:

*Libraries* are programs that cannot be used as stand-alone commands, but are used by other programs. For example, a program that makes it easier for other programs to render images. :books:

You can use the command `which <command>` to quickly find out where the executable file of a program is located.

- `/bin`: Contains general-purpose programs that can be used when only the root partition is mounted. This directory contains only very basic scripts. It is generally not a good idea to place your own scripts here.
- `/lib`: Contains libraries required by programs that can run when only the root partition is mounted.
- `/lib64`: Same as `/lib`, but for 64-bit programs.
- **`/usr/bin`**: Most pre-installed programs are in here. Most programs you install with package managers (such as aptitude or yum) are in here as well.
- `/usr/games`: Contains game programs.
- `/usr/lib`: Contains the libraries for most programs.
- `/usr/lib64`: Same as `/usr/lib`, but for 64-bit programs.
- `/usr/libexec`: Some libraries need binaries that are only used by libraries, not by normal programs. Those binaries go in here.
- **`/usr/local/bin`**: Some programs install other programs. Those programs go in here. (Except for package managers.) For example, `pip` installs python modules in here. This is also a good place to put custom scripts that should be accessible for all users on the system.
- `/usr/local/games`: Contains game programs. If you compiled a game yourself, you could place it here.
- `/usr/local/lib`: Libraries installed by users or programs other than package managers.
- `/usr/local/sbin`: The *s* stands for *system*. For local system administration programs. If you compiled a system administration program yourself, you could place it in here.
- `/usr/sbin`: Programs for system administration are in here. These programs can only be used when the `/usr` partition can be mounted. These programs can also be used when the system is booting.
- `/sbin`: Contains system binaries. Because this is in the root partition, these scripts can be used when only the root partition is mounted. Most of these programs are used for system maintenance.
