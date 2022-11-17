# Git Config

Some configurations for Git.

Specially useful for those who reinstall their systems a lot.

## Basic configuration

```
git config --global user.name <name>
git config --global user.email <email>
```

## Want to sign your commits?

```
git config --global user.signingkey <key_id>
git config --global commit.gpgsign true
```

*You can get your key ID with `gpg --list-keys --keyid-format LONG`.*

## Using Windows?

You might need to specify the location of GPG.

```
git config --global gpg.program <location>
```

*<sup>1: </sup>You might have to use double backslashes to separate directories `\\`.*

*<sup>2: </sup>If the path has spaces, you should wrap it with quotes ("" or '').*

## Using Linux?

You might run into the following issue when trying to sign your commits:

```
error: gpg failed to sign the data
fatal: failed to write commit object
```

Generally you can fix (temporarily) it by running:

```
export GPG_TTY=$(tty)
```

_Psst!: You can add that line to your `~/.bashrc` or `~/.bash_profile` file._

## Using Unicode?

You can make `git status` show your tildes and other weird characters by running:

```
git config --global core.quotepath off
```