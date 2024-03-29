# Droplr Bash

Basic Droplr implementation for Linux written in Bash.

Currently, Droplr has no native Linux client besides browser extensions (Chrome only).

The advantage of this script is its completely agnostic. You can use any screenshot software, recording software, or simply drop files and it will process them for you.

There are two modes to this script described below.

## Watching

Will watch a set directory for new files (created or moved into the directory).

It will then upload to your Droplr account and copy the share URL to your clipboard.

![Sample](sample.gif?raw=true "Sample")

## Latest

This will grab the latest file in the set directory and upload to your Droplr account and copy the share URL to your clipboard.

## Installation

First, you'll need the following libraries:

+ `inotify-tools` (required) For watching the directory
+ `curl` (required) For sending cURL commands
+ `jq` (required) For paring the response
+ `ffmpeg` (optional) If you plan on having videos converted for you
+ `notify-send` (optional) To send notification to desktop

Next, create a file `$XDG_CONFIG_HOME/droplr-bash/config` (ex: `~/.config/droplr-bash/config`) with the contents corrected from `./config.sample` in this repo.

## Usage

`chmod +X droplr`

### Watching

Will watch continuously and upload on-demand of seeing a new file.

#### Screenshots

Run `droplr watch screenshots`.

#### Screencasts

Run `droplr watch screencasts`.

### Latest

Will grab the latest file and upload it directly.

#### Screenshots

Run `droplr screenshots`.

#### Screencasts

Run `droplr screencasts`.

## Recommendations

Setup a keyboard shortcut for screenshots...

* `Super + Shift + S` for screenshots, mapped to `droplr screenshots`
* `Super + Shift + V` for screencasts, mapped to `droplr screencasts`
