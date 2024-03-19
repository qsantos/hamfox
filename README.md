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
$ gluon download   # Download Firefox source code, about 500 MB to download
$ gluon bootstrap  # Install dependencies, takes a couple minutes
$ gluon import     # Apply patches for HamFox, instant
$ gluon build      # Compile HamFox
$ gluon run        # Start Hamfox
```

**Note:**
Compiling `gkrust` takes about of memory 11 GB.
So either have more memory available, or enable swap and wait an hour or two…
`export RUSTFLAGS="-Cdebuginfo=0"` might help.
