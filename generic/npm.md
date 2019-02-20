# Assumptions

You've already installed it via your distro's repositories

# Don't Require SUDO with `install -g`

Create a directory for global installations:

```
$ mkdir ~/.npm-global
```

Configure npm to use the new directory path:

```
$ npm config set prefix '~/.npm-global'
```

In your shell profile file (i.e. `~/.zshrc` for ZSH) add the following to add the new folder to your `$PATH` variable:

```
export PATH=~/.npm-global/bin:$PATH
```

Update your system variables (again using ZSH as the example):

```
source ~/.zshrc
```
