# Keypass

A simple password management utility for Keybase.io

## How It Works

Keypass uses `keybase` to encrypt a list of passwords and store them where you
specify. Adding more password entries decrypts the file, adds the new entry
then re-encrypts it.

## Prerequisites

* [keybase.io](http://keybase.io) account
* Bash

## Installation

* Set the **KEYBASE_USER** and **PASS_DIR** variables in `keypass` to something reasonable
* Probably put `keypass` in your **PATH**

## Usage

```
keypass { list ["TERM"] | add URL USER PASS ["DESC"] | gen [LENGTH] | interactive }

COMMANDS:
  list ["TERM"]                 Decrypt and list passwords, optionally matching "TERM"
  add URL USER PASS ["DESC"]    Add the url, username and password with optional description
  gen [LENGTH]                  Generate a new password with optional length
  interactive                   Interactively edit the password file with $EDITOR

INFO:
  * You can use the first letter of each command as a shortcut (e.g `keypass i` for interactive mode.
  * Interactive is the only command that will generate (and clean up) a temporary file.
```

## Protips

* Add `export HISTIGNORE=$HISTIGNORE:keypass*` to your `.bash_profile` so passwords aren't saved in your history
