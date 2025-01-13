# Using zlib on all operating systems

## Linux

List of packages to install when building and running applications using zlib:

| Distro                    | Build         | Run
| ------------------------- | ------------- | ----------
| Ubuntu, Debian, Mint      | zlib1g-dev    | zlib1g
| Fedora, Red Hat, openSUSE | zlib-devel    | zlib
| Arch                      | zlib          | zlib
| Alpine                    | zlib-dev      | zlib
| Gentoo                    | sys-libs/zlib | sys-libs/zlib

Build options:
~~~
LDLIBS += -lz
~~~

## macOS

A version of zlib is installed with macOS and another one comes with HomeBrew.
Let's assume we use the native zlib coming with macOS.

Build options:
~~~
LDLIBS += -lz
~~~

In HomeBrew formulae:
~~~
uses_from_macos "zlib"
~~~

## BSD

List of packages to install to build and run applications using zlib:

| Distro                | Build        | Run
| --------------------- | ------------ | ----------
| FreeBSD, DragonFlyBSD | (in base OS) | (in base OS)
| OpenBSD, NetBSD       | zlib         | zlib

## pkgconfig

Applications using zlib directly:
~~~
Requires: zlib
~~~

Libraries using zlib internally (e.g. libtsduck):
~~~
Requires.private: zlib
~~~

## Windows

The standard Windows DLL `PresentationNative_v0300.dll` embeds a version of zlib with the following exported symbols:
- `ums_deflate_init`
- `ums_deflate`
- `ums_inflate_init`
- `ums_inflate`

However, there is no documentation, examples are scarce and vague, there is not `deflate_end` or `inflate_end`
and the status of memory allocation in the middle of an operation is unclear.

Alteratively, we may use the header-only implementation from https://github.com/vurtun/lib

There is one single file for deflate and one for inflate.
The license is dual: MIT and Public Domain.
The code can be used without restriction.

## References

- Zlib home page: https://zlib.net/
- Header-only implementations:
  - https://github.com/vurtun/lib
