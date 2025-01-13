## Using zling on all operating systems

### pkgconfig

Applications using zlib directly:
~~~
Requires: zlib
~~~

Libraries using zlib internally (e.g. libtsduck):
~~~
Requires.private: zlib
~~~

### Linux

List of packages to install to build and run applications using zlib:

| Distro   | Build       | Run
| -------- | ----------- | ----------
| Ubuntu   | zlib1g      | zlib1g-dev
| Debian   |             |
| Mint     |             |
| Fedora   |             |
| Red Hat  |             |
| openSUSE |             |
| Arch     |             |
| Alpine   |             |
| Gentoo   |             |

Build options:
~~~
LDLIBS += -lz
~~~

### macOS

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

### BSD

List of packages to install to build and run applications using zlib:

| Distro       | Build       | Run
| ------------ | ----------- | ----------
| FreeBSD      |             |
| OpenBSD      |             |
| NetBSD       |             |
| DragonFlyBSD |             |

### Windows

The standard Windows DLL `PresentationNative_v0300.dll` embeds a version of zlib with the following exported symbols:
- `ums_deflate_init`
- `ums_deflate`
- `ums_inflate_init`
- `ums_inflate`

However, there is no documentation, examples are scarce are vague, there is not `deflate_end` or `inflate_end`
and the status of memory allocation is vague.

Alteratively, we may use the header-only implementation from https://github.com/vurtun/lib

There is one single file for deflate and one for inflate.
The license is dual: MIT and Public Domain.
The code can be used without restriction.

### References

- Zlib home page: https://zlib.net/
- Header-only implementations:
  - https://github.com/vurtun/lib
- Header-only wrapper projects:
  - https://github.com/mateidavid/zstr
  - https://github.com/tmaklin/bxzstr
