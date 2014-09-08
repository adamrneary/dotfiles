# Dotfiles

> I attack the structure Wolvie Berzerker style, and knock out the fuckin' pin and bickety bam, the motherfucker is rubble. Hence, no game show.

## Credit first

* [holman](https://github.com/holman/dotfiles), who thanks
* [ryanb](http://github.com/ryanb/dotfiles)
* [mathiasbynens](https://github.com/mathiasbynens/dotfiles)
* [thoughtbot](https://github.com/thoughtbot/dotfiles)

Thanks, all.

## Install

Run this:

```sh
git clone https://github.com/adamrneary/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
script/bootstrap
```

This will symlink the appropriate files in `.dotfiles` to your home directory.
Everything is configured and tweaked within `~/.dotfiles`.

The main file you'll want to change right off the bat is `zsh/zshrc.symlink`,
which sets up a few paths that'll be different on your particular machine.

`dot` is a simple script that installs some dependencies, sets sane OS X
defaults, and so on. Tweak this script, and occasionally run `dot` from
time to time to keep your environment fresh and up-to-date. You can find
this script in `bin/`.

Additional install moves:

* `script/install` will execute the install scripts in each topic folder
* `homebrew/cask` will install os x native apps like a boss

## Components

There's a few special files in the hierarchy.

- **bin/**: Anything in `bin/` will get added to your `$PATH` and be made
  available everywhere.
- **topic/\*.zsh**: Any files ending in `.zsh` get loaded into your
  environment.
- **topic/path.zsh**: Any file named `path.zsh` is loaded first and is
  expected to setup `$PATH` or similar.
- **topic/completion.zsh**: Any file named `completion.zsh` is loaded
  last and is expected to setup autocomplete.
- **topic/\*.symlink**: Any files ending in `*.symlink` get symlinked into
  your `$HOME`. This is so you can keep all of those versioned in your dotfiles
  but still keep those autoloaded files in your home directory. These get
  symlinked in when you run `script/bootstrap`.

## Topical

Everything's built around topic areas. If you're adding a new area to your
forked dotfiles — say, "Java" — you can simply add a `java` directory and put
files in there. Anything with an extension of `.zsh` will get automatically
included into your shell. Anything with an extension of `.symlink` will get
symlinked without extension into `$HOME` when you run `script/bootstrap`.

## iTerm

For iTerm copy the config to ~/Library/Preferences:

`cp ~/.dotfiles/com.googlecode.iterm2.plist ~/Library/Preferences/`
