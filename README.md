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
$ sudo npm install -g gluon-build@latest
$ gluon download   # Download Firefox source code, 500 MB to download and unpack, takes a couple minutes
$ gluon bootstrap  # Install dependencies, takes a couple minutes
$ gluon import     # Apply patches for HamFox, instant
$ gluon build      # Compile HamFox, takes a couple hours
$ gluon run        # Start Hamfox, takes a couple seconds
```

**Note:**
Compiling `gkrust` requires 11 GB of free memory, and takes about 10 minutes.
If there is not enough memory, the build will fail with the message below.
If that happens, free up some memory by killing some applications (e.g. Firefox), and run `gluon build` again to resume the build.
If you cannot make this amount of memory available, enable swap, but note that this will make the final part of the build very long.

```
process didn't exit successfully: `/home/user/.mozbuild/sccache/sccache /home/user/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/bin/rustc --crate-name gkrust […]
```
