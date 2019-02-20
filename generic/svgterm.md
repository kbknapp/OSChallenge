# Pre-Reqs

* `npm` is installed
* `asciinema` is installed

# Install `svg-term`

**NOTE:** To not require `sudo` follow [./npm.md](./npm.md)

```
$ npm install -g svg-term-cli
```

After making a recording with `asciinema`, convert it to an SVG:

```
$ svg-term --cast=219486 --out ~/somewhere/out.svg --padding 18 --height 8 --width 80
```
