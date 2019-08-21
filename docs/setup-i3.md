# Setup i3 Window Manager

## Install i3

From command line install required dependencies and set i3 in `.xinit.rc`:

```bash
$ sudo apt install xinit i3 dmenu suckless-tools
$ echo "exec i3" > .xinit.rc
```

To start i3 type:

```bash
$ startx
```

And enjoy.

## References

- [Easily run I3 on raspberrypi](https://steemit.com/raspberry/@joedoe47/easily-run-i3-on-raspberrypi),
  by [joedoe47](https://steemit.com/@joedoe47). _(Last accessed: 2019-08-21.)_
