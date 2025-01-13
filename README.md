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

In Homebrew formulae:
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

### References

- Zlib home page: https://zlib.net/
- Header-only wrapper projects:
  - https://github.com/mateidavid/zstr
  - https://github.com/tmaklin/bxzstr
