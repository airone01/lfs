ft_linux — Package Analysis Against LFS Book 12.4
==================================================

Cross-reference of the mandatory package list from the ft_linux subject (v3.6)
against LFS Book 12.4. Packages are split into three sections:

1. **Installed** – present in LFS 12.4, with verification hints.
2. **Deprecated / Removed / Replaced** – present in the subject but no longer
   part of LFS 12.4, with an explanation.
3. **Renamed / Rebranded** – same upstream software, different name.

.. note::

   LFS 12.4 ships in two editions: *SysV* and *Systemd*. Notes that differ
   between the two are marked accordingly. The subject package list (Sysklogd +
   Sysvinit) targets a SysV-style system. I went for a SysV build.

----

Installed Packages
==================

These packages are present in LFS 12.4 exactly as listed in the subject.
Because LFS has no package manager by default, the canonical way to confirm
installation is to query the installed binary or library directly.
Some executables do not have a version flag and must be run to expose the usage
tooltip, others are libraries and don't expose have executables at all.
For those, please list the files to prove they are installed.

Acl
---
:Verify: ``getfacl --version``
:Path:   ``/usr/bin/getfacl``, ``/usr/lib/libacl.so``

Attr
----
:Verify: ``attr`` 
:Path:   ``/usr/bin/attr``, ``/usr/lib/libattr.so``

Autoconf
--------
:Verify: ``autoconf --version``
:Path:   ``/usr/bin/autoconf``

Automake
--------
:Verify: ``automake --version``
:Path:   ``/usr/bin/automake``

Bash
----
:Verify: ``bash --version``
:Path:   ``/bin/bash``

Bc
--
:Verify: ``bc --version``
:Path:   ``/usr/bin/bc``

Binutils
--------
:Verify: ``ld --version``, ``as --version``
:Path:   ``/usr/bin/ld``, ``/usr/bin/as``, ``/usr/lib/libbfd*.so``

Bison
-----
:Verify: ``bison --version``
:Path:   ``/usr/bin/bison``

Bzip2
-----
:Verify: ``bzip2 --version``
:Path:   ``/usr/bin/bzip2``, ``/usr/lib/libbz2.so``

Check
-----
:Verify: ``pkg-config --modversion check``  (or ``ls /usr/lib/libcheck*``)
:Path:   ``/usr/lib/libcheck.so``
:Note:   Not present in LFS 12.4 anymore. Installed for the sake of it the
         the correction.

Coreutils
---------
:Verify: ``ls --version``  (ls is provided by coreutils)
:Path:   ``/usr/bin/ls``, ``/usr/bin/cp``, ``/usr/bin/chmod``, etc.

DejaGNU
-------
:Verify: ``runtest --version``
:Path:   ``/usr/bin/runtest``
:Note:   Used only for running the GCC and Binutils test suites; not needed
         after the build.

Diffutils
---------
:Verify: ``diff --version``
:Path:   ``/usr/bin/diff``

E2fsprogs
---------
:Verify: ``/usr/sbin/e2fsck``
:Path:   ``/usr/sbin/e2fsck``, ``/usr/lib/libe2p.so``, ``/usr/lib/libext2fs.so``

Expat
-----
:Verify: ``xmlwf --version``  (ships with expat) or ``ls /usr/lib/libexpat*``
:Path:   ``/usr/lib/libexpat.so``

Expect
------
:Verify: ``expect -v``
:Path:   ``/usr/bin/expect``, ``/usr/lib/expect*/``
:Note:   Used only during test suites (GCC, Binutils); can be absent after
         the build without affecting the running system.

File
----
:Verify: ``file --version``
:Path:   ``/usr/bin/file``, ``/usr/lib/libmagic.so``

Findutils
---------
:Verify: ``find --version``
:Path:   ``/usr/bin/find``, ``/usr/bin/locate``

Flex
----
:Verify: ``flex --version``
:Path:   ``/usr/bin/flex``

Gawk
----
:Verify: ``gawk --version``
:Path:   ``/usr/bin/gawk``

GCC
---
:Verify: ``gcc --version``, ``g++ --version``
:Path:   ``/usr/bin/gcc``, ``/usr/lib/libgcc_s.so``, ``/usr/lib/libstdc++.so``

GDBM
----
:Verify: ``ls /usr/lib/libgdbm*``
:Path:   ``/usr/lib/libgdbm.so``, ``/usr/include/gdbm.h``

Gettext
-------
:Verify: ``gettext --version``
:Path:   ``/usr/bin/gettext``, ``/usr/lib/libintl.so``

Glibc
-----
:Verify: ``/usr/lib/libc.so.6``  (execute it directly to see version)
:Path:   ``/usr/lib/libc.so.6``, ``/usr/lib/ld-linux-x86-64.so.2``

GMP
---
:Verify: ``ls /usr/lib/libgmp*``
:Path:   ``/usr/lib/libgmp.so``, ``/usr/include/gmp.h``

Gperf
-----
:Verify: ``gperf --version``
:Path:   ``/usr/bin/gperf``

Grep
----
:Verify: ``grep --version``
:Path:   ``/usr/bin/grep``

Groff
-----
:Verify: ``groff --version``
:Path:   ``/usr/bin/groff``

GRUB
----
:Verify: ``/usr/sbin/grub-install --version``
:Path:   ``/usr/sbin/grub-install``, ``/boot/grub/``

Gzip
----
:Verify: ``gzip --version``
:Path:   ``/usr/bin/gzip``

Iana-Etc
--------
:Verify: ``cat /etc/services | head -n4``, ``cat /etc/protocols | head -n4``
:Path:   ``/etc/services``, ``/etc/protocols``
:Note:   This package is purely data files; there are no binaries.

Inetutils
---------
:Verify: ``hostname --version``
:Path:   ``/usr/bin/hostname``, ``/usr/bin/ping``, ``/usr/bin/ftp``

IPRoute2
--------
:Verify: ``/usr/sbin/ss --version``
:Path:   ``/usr/sbin/ip``, ``/usr/sbin/ss``

Kbd
---
:Verify: ``loadkeys --version``
:Path:   ``/usr/bin/loadkeys``, ``/usr/bin/setfont``

Kmod
----
:Verify: ``kmod --version``
:Path:   ``/usr/bin/kmod``; also provides ``lsmod``, ``modprobe``, ``insmod``
         as symlinks.

Less
----
:Verify: ``less --version``
:Path:   ``/usr/bin/less``

Libcap
------
:Verify: ``/usr/sbin/capsh --version``  (or ``ls /usr/lib/libcap*``)
:Path:   ``/usr/lib/libcap.so``, ``/usr/sbin/setcap``

Libpipeline
-----------
:Verify: ``ls /usr/lib/libpipeline*``
:Path:   ``/usr/lib/libpipeline.so``
:Note:   Used by man-db; no standalone binary.

Libtool
-------
:Verify: ``libtool --version``
:Path:   ``/usr/bin/libtool``

M4
--
:Verify: ``m4 --version``
:Path:   ``/usr/bin/m4``

Make
----
:Verify: ``make --version``
:Path:   ``/usr/bin/make``

Man-DB
------
:Verify: ``man --version``
:Path:   ``/usr/bin/man``, ``/usr/bin/mandb``

Man-pages
---------
:Verify: ``man 2 open``  (check a syscall man page)
:Path:   ``/usr/share/man/man2/``, ``/usr/share/man/man3/``
:Note:   Data files only; no binaries.

MPC
---
:Verify: ``ls /usr/lib/libmpc*``
:Path:   ``/usr/lib/libmpc.so``, ``/usr/include/mpc.h``

MPFR
----
:Verify: ``ls /usr/lib/libmpfr*``
:Path:   ``/usr/lib/libmpfr.so``, ``/usr/include/mpfr.h``

Ncurses
-------
:Verify: ``ls /usr/lib/libncurses*``
:Path:   ``/usr/lib/libncurses.so``, ``/usr/bin/tput``

Patch
-----
:Verify: ``patch --version``
:Path:   ``/usr/bin/patch``

Perl
----
:Verify: ``perl --version``
:Path:   ``/usr/bin/perl``, ``/usr/lib/perl5/``

Procps (procps-ng)
------------------
:Verify: ``ps --version``
:Path:   ``/usr/bin/ps``, ``/usr/bin/top``, ``/usr/lib/libprocps.so``
:Note:   The subject calls it "Procps"; in LFS 12.4 it is explicitly
         *procps-ng*, the maintained fork. Functionally identical for the
         purposes of this project.

Psmisc
------
:Verify: ``pstree --version``
:Path:   ``/usr/bin/pstree``, ``/usr/bin/fuser``, ``/usr/bin/killall``

Readline
--------
:Verify: ``ls /usr/lib/libreadline*``
:Path:   ``/usr/lib/libreadline.so``, ``/usr/include/readline/``

Sed
---
:Verify: ``sed --version``
:Path:   ``/usr/bin/sed``

Shadow
------
:Verify: ``/usr/sbin/useradd``
:Path:   ``/usr/sbin/useradd``, ``/usr/bin/passwd``

Sysklogd
--------
:Verify: ``/sbin/syslogd -v``  (or ``ls /sbin/syslogd``)
:Path:   ``/sbin/syslogd``, ``/sbin/klogd``
:Note:   **SysV edition only.** If you built the Systemd edition of LFS 12.4,
         journald from systemd replaces syslogd entirely and this package is
         absent.

Sysvinit
--------
:Verify: ``/sbin/init --version``
:Path:   ``/sbin/init``
:Note:   **SysV edition only.** Not present in the Systemd edition; systemd
         provides ``/sbin/init`` as a symlink to itself instead.

Tar
---
:Verify: ``tar --version``
:Path:   ``/usr/bin/tar``

Tcl
---
:Verify: ``tclsh``  (type ``info patchlevel`` at the prompt)
:Path:   ``/usr/bin/tclsh*``, ``/usr/lib/libtcl*.so``
:Note:   Required only to run DejaGNU / Expect test suites; not needed on
         the final system but is included in LFS 12.4 nonetheless.

Texinfo
-------
:Verify: ``makeinfo --version``  (or ``texi2any --version``)
:Path:   ``/usr/bin/makeinfo``

Time Zone Data (tzdata)
-----------------------
:Verify: ``ls /usr/share/zoneinfo/``
:Path:   ``/usr/share/zoneinfo/``, ``/etc/localtime``
:Note:   Data files only; installed by the Glibc chapter in LFS 12.4.

Util-linux
----------
:Verify: ``mount --version``
:Path:   ``/usr/bin/mount``, ``/usr/bin/fdisk``, ``/usr/bin/lsblk``,
         ``/usr/lib/libuuid.so``, ``/usr/lib/libblkid.so``

Vim
---
:Verify: ``vim --version``
:Path:   ``/usr/bin/vim``

XML::Parser
-----------
:Verify: ``head /usr/lib/perl5/5.42/site_perl/XML/Parser.pm | head -n7"``
:Path:   ``head /usr/lib/perl5/5.42/site_perl/XML/Parser.pm``
:Note:   Perl module.

Xz Utils
--------
:Verify: ``xz --version``
:Path:   ``/usr/bin/xz``, ``/usr/lib/liblzma.so``

Zlib
----
:Verify: ``ls /usr/lib/libz*``
:Path:   ``/usr/lib/libz.so``, ``/usr/include/zlib.h``

----

Deprecated / Removed / Replaced Packages
=========================================

These packages appear in the subject's mandatory list but are **not** installed
by LFS 12.4, either because they have been removed from the book, superseded
by another package, or absorbed into a different source tarball.

Eudev
-----
:Status:      **Replaced** by udev from the systemd source tarball.
:Subject ref: Listed as the kernel-module loader (equivalent to udev).
:What LFS 12.4 does:
   Starting with LFS 11.x, the book dropped the standalone *Eudev* fork.
   In the **SysV edition**, LFS 12.4 downloads the *systemd* source tarball
   and builds *only* the udev component from it (``/usr/lib/udev/``,
   ``/usr/bin/udevadm``). In the **Systemd edition**, full systemd is used and
   udev is part of it. Eudev, which was a community fork of udev intended for
   non-systemd systems, is no longer necessary because the build procedure
   extracts the udev piece directly.
:Verify (LFS 12.4 SysV):
   ``udevadm --version`` and ``ls /usr/lib/udev/rules.d/``

Intltool
--------
:Status:      **Removed** from LFS (dropped around LFS 9.x).
:Subject ref: Listed as a required package in the mandatory part.
:Why removed:
   Intltool was a Perl-based toolchain for extracting translatable strings
   from source files and merging them with gettext ``.po`` files. Modern
   projects have migrated to using ``gettext`` autotools macros or the
   ``xgettext``/``msgfmt`` workflow directly, making Intltool redundant.
   The LFS editors removed it once no remaining LFS package required it as
   a build dependency. You may encounter it in BLFS (some older GTK
   applications still need it), but it is absent from the base LFS 12.4
   build.

Pkg-config
----------
:Status:      **Replaced** by *pkgconf* since LFS 12.0.
:Subject ref: Listed under its original name "Pkg-config".
:Why replaced:
   The original ``pkg-config`` binary (freedesktop.org) has seen minimal
   maintenance for years. LFS 12.0 switched to *pkgconf*, an independently
   written, fully compatible, and actively maintained replacement. pkgconf
   installs a ``/usr/bin/pkg-config`` symlink, so all existing scripts and
   build systems remain unaffected.
:Verify: ``pkg-config --version``  (reports pkgconf's version number)
:Path:   ``/usr/bin/pkgconf``, symlinked as ``/usr/bin/pkg-config``

Udev-lfs Tarball
----------------
:Status:      **Deprecated / Removed**.
:Subject ref: Listed as a distinct package "Udev-lfs Tarball".
:Why removed:
   This was a small, LFS-project-maintained tarball containing supplementary
   udev rules and helper shell scripts that were not shipped with either eudev
   or upstream udev. It filled the gap when LFS was transitioning between udev
   versions. As of LFS 11.x, all required udev rules are either upstream (in
   the systemd/eudev source itself) or generated at runtime by udevadm. The
   separate tarball became unnecessary and was dropped from the book entirely.

----

Summary Table
=============

+----------------------+-----------+----------------------------------------------+
| Package              | Status    | Notes                                        |
+======================+===========+==============================================+
| Acl                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Attr                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Autoconf             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Automake             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Bash                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Bc                   | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Binutils             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Bison                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Bzip2                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Check                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Coreutils            | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| DejaGNU              | Installed | Test-suite tool only                         |
+----------------------+-----------+----------------------------------------------+
| Diffutils            | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Eudev                | REPLACED  | udev from systemd tarball used instead       |
+----------------------+-----------+----------------------------------------------+
| E2fsprogs            | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Expat                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Expect               | Installed | Test-suite tool only                         |
+----------------------+-----------+----------------------------------------------+
| File                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Findutils            | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Flex                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Gawk                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| GCC                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| GDBM                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Gettext              | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Glibc                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| GMP                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Gperf                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Grep                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Groff                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| GRUB                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Gzip                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Iana-Etc             | Installed | Data files only (/etc/services, /etc/        |
|                      |           | protocols)                                   |
+----------------------+-----------+----------------------------------------------+
| Inetutils            | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Intltool             | REMOVED   | Dropped ~LFS 9.x; gettext covers its role    |
+----------------------+-----------+----------------------------------------------+
| IPRoute2             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Kbd                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Kmod                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Less                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Libcap               | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Libpipeline          | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Libtool              | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| M4                   | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Make                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Man-DB               | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Man-pages            | Installed | Data files only                              |
+----------------------+-----------+----------------------------------------------+
| MPC                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| MPFR                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Ncurses              | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Patch                | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Perl                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Pkg-config           | REPLACED  | pkgconf used; provides pkg-config symlink    |
+----------------------+-----------+----------------------------------------------+
| Procps               | Installed | Ships as procps-ng in LFS 12.4               |
+----------------------+-----------+----------------------------------------------+
| Psmisc               | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Readline             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Sed                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Shadow               | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Sysklogd             | Installed | SysV edition only                            |
+----------------------+-----------+----------------------------------------------+
| Sysvinit             | Installed | SysV edition only                            |
+----------------------+-----------+----------------------------------------------+
| Tar                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Tcl                  | Installed | Test-suite tool only                         |
+----------------------+-----------+----------------------------------------------+
| Texinfo              | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Time Zone Data       | Installed | Installed as part of Glibc chapter           |
+----------------------+-----------+----------------------------------------------+
| Udev-lfs Tarball     | REMOVED   | Rules now upstream in systemd/eudev          |
+----------------------+-----------+----------------------------------------------+
| Util-linux           | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Vim                  | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| XML::Parser          | Installed | Perl module                                  |
+----------------------+-----------+----------------------------------------------+
| Xz Utils             | Installed |                                              |
+----------------------+-----------+----------------------------------------------+
| Zlib                 | Installed |                                              |
+----------------------+-----------+----------------------------------------------+

