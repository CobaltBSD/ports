# ports
CobaltBSD ports tree. Currently a stub.

## Ports Guidelines
All free software can be submitted to the official ports tree. However, there are quality controls and guidelines which must be followed for software to be accepted. Explicitly disallowed submissions are the following:
* All software that is either non-free or solely used in tandem with other non-free software (e.g. non-free drivers, some game launchers)
* Packages that are unusably incomplete, very unstable or broken by default
* Libraries that are not utilized by any other packages in the ports tree
* Software with known unpatched vulnerabilities
* Multiple versions of the same package, unless needed for compatibility

Furthermore, where applicable, software should be pledged and unveiled appropriately.

Due to a variety of ethical and/or technical issues, use of the following packages are discouraged. Wherever possible, such ports should have these dependencies disabled:
* D-Bus - Insecure by design and buggy. It is included in the ports simply due to the large number of Linux-centric packages in the ports tree that benefit from it.
* GLib - Extraordinarely bloated, reimplements much of the C++ STL in C. Used by a number of desktop components, particularly related to GNOME and Xfce.
* Anything written in Rust or other less common languages - It's never fun to have to install a completely new compiler toolchain for a single desktop widget or utility. Furthermore, many of them use far more system resources than traditional C/C++ compilers, and thus may struggle compiling on lower-end systems.
* OpenSSL - LibreSSL is the preferred TLS/SSL implementation. Unless unrealistic (i.e GNU IceCat), packages should be patched to support LibreSSL.

The following packages will never be available in the ports tree for outstanding issues similar to the ones described above:
* Chromium - Due to its size, will not even compile in one try on the vast majority of systems. In order for a port to be useful, it would need to be distributed as a pre-compiled binary, which we do not have the resources for or interest in doing.
* QtWebEngine - It is Chromium but with gaping vulnerabilities everywhere, due to being intentionally out of date.
* PolKit - A hotspot of security problems. Thankfully, very few packages outside of Linux ask for it.
* Wayland - Wayland support has been experimentally tested on OpenBSD with some success, but CobaltBSD intends to stick with the X display system indefinitely. In our view, the Wayland display system does not provide any substantial, demonstrated benefits and has numerous fundamental issues that make it a worse choice as a lightweight desktop.
* Firefox/Librewolf - GNU IceCat is the primary large browser available in the ports tree. Firefox and Librewolf are excluded simply to avoid redundancy of having multiple nearly-identical large browsers.

[HyperbolaBSD has an excellent page describing in detail the issues with many of the packages listed above, and that we largely agree with.](https://wiki.hyperbola.info/doku.php?id=en:philosophy:incompatible_packages)
