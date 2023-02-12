```
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
