# go-homedir

The following tweet shows the original author of **go-homedir** is archiving his version in early 2024. and will not be accepting any PRs or take action on any issues any longer.  

**See his post on Twitter/X:**

> _I&#39;m planning on archiving ~15 of my Go libs early in 2024. I don&#39;t write Go anymore and I no longer actively use these libraries so I&#39;d rather be transparent and be able to move on from them. I welcome any forks! Here is more info and the [list of repos](https://gist.github.com/mitchellh/90029601268e59a29e64e55bab1c5bdc). <br>&mdash; Mitchell Hashimoto (@mitchellh) [December 19, 2023](href="https://twitter.com/mitchellh/status/1737226562519593207?ref_src=twsrc%5Etfw">)_

I have used this package in many of my projects so I decided to fork and offer to maintain it.

## As such [Feature](https://github.com/mikeschinkel/go-homedir/issues) [Requests](https://github.com/mikeschinkel/go-homedir/discussions) are welcome!


## Overview
This is a Go library for detecting the user's home directory without
the use of cgo, so the library can be used in cross-compilation environments.

Usage is incredibly simple, just call `homedir.Dir()` to get the home directory
for a user, and `homedir.Expand()` to expand the `~` in a path to the home
directory.

## FAQ
1. **Why not just use `os/user`?** The built-in `os/user` package requires
cgo on Darwin systems. This means that any Go code that uses that package
cannot cross compile. But 99% of the time the use for `os/user` is just to
retrieve the home directory, which we can do for the current user without
cgo. This library does that, enabling cross-compilation.
