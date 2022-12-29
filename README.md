## Arch Linux Pacman package for http-to-https-letsencrypt

### To install http-to-https-letsencrypt as Pacman package:

- Make sure you have Rust and base-devel package installed.

> pacman -S rust
> 
> pacman -S base-devel

- Clone repository

> cd http-to-https-letsencrypt-arch-package
> 
> makepkg

- You may need to run commands listed below as an administrator

Replace _VERSION_ with version you've built.

> pacman -U http-to-https-letsencrypt-_VERSION_.pkg.tar.zst


### Test installation:
> http-to-https-letsencrypt

Press Ctrl + C (or CMD + C) to stop server.

### To remove http-to-https-letsencrypt:
> pacman -Rs http-to-https-letsencrypt
