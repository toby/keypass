# Keypass
A simple password management utility for Keybase.io

## Prerequisites
* [keybase.io](http://keybase.io) account
* Bash

## Installation
* Set the **KEYBASE_USER** and **PASS_DIR** variables in `keypass` to something reasonable
* Probably put `keypass` in your **PATH**

## Usage
* `keypass add myurl.com myuser mypass` - create a new password entry
* `keypass add myurl.com myuser mypass "some sort of description"` - you can add optional descriptions
* `keypass list` - list all password entries
* `keypass list "search for something"` - add an optional term for a case-insensitive search

## How It Works
Keypass uses `keybase` to encrypt a list of passwords and store them where you specify. Adding more password entries decrypts the file, adds the new entry then re-encrypts it. No temp files are used as it all happens with standard in and out. Same deal with `list`ing.

## Protips
* To delete an entry, manually decrypt it with `keybase` then edit and re-encrypt it
* Add `export HISTIGNORE=$HISTIGNORE:keypass*` to your `.bash_profile` so passwords aren't saved in your history
