# HamFox

Encryption-less Variant of Firefox for amateur radio

International bodies and local governments grants special rights to operators of the [amateur radio service](https://en.wikipedia.org/wiki/Amateur_radio).
This allows free tinkering and experimentation with wireless technology.
In exchange, all communications should be performed [in the clear](https://qsantos.fr/2022/12/21/ham-crypto/).

However, this does not preclude the use of cryptography altogether.
This project allows using HTTPS over in the amateur radio service, such as [AMPRNet](https://en.wikipedia.org/wiki/AMPRNet).
This can be useful for server authentication, and to enable services with secure accounts using [client authentication](https://blog.cloudflare.com/introducing-tls-client-auth/).

**Note:** all communications are unencrypted, **do not use passwords** when browsing with HamFox

See also [HamSSH](https://github.com/qsantos/hamssh).

# Installation

```
$ sudo apt install python3 mercurial
$ python3 bootstrap.py --no-interactive --no-system-changes --application-choice=browser
$ cd mozilla-unified
$ patch -p1 <../null-only.patch
$ ./mach build
$ ./mach run
```

**Note:**
Compiling `gkrust` requires 11 GB of free memory, and takes about 10 minutes.
If there is not enough memory, the build will fail with the message below.
If that happens, free up some memory by killing some applications (e.g. Firefox), and run `./mach build` again to resume the build.
If you cannot make this amount of memory available, enable swap, but note that this will make the final part of the build very long.

```
process didn't exit successfully: `/home/user/.mozbuild/sccache/sccache /home/user/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name gkrust […]
```
