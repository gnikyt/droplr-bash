# Droplr Bash

Basic Droplr implementation for Linux written in Bash.

This script will watch a set directory for new files (created or moved into the directory). It will then upload to your Droplr account and copy the share URL to your clipboard.

Currently, Droplr has no native Linux client or Firefox extension. The advantage of this script is its completely agnostic; you can use any screenshot software, recording software, or simply drop files into the watched directory and it will process them for you.

![Sample](sample.gif?raw=true "Sample")

## Installation

First, you'll need the following libraries:

+ `inotify-tools` (required) For watching the directory
+ `curl` (required) For sending cURL commands
+ `xclip` (required) to copy the public upload link to your clipboard.
+ `ffmpeg` (optional) If you plan on having videos converted for you
+ `notify-send` (optional) To send notification to desktop

Next, create a file `$XDG_CONFIG_HOME/droplr-bash/config` (ex: `~/.config/droplr-bash/config`) with the following contents:

```conf
watch_dir=/home/(yourname)/(somedir)/droplr # Directory to watch
username="your-email"
password="yout-password"
convert_video=1 # 1 = Convert videos to MP4, 0 = Leave them as-is
notify=1 # 1 = Use notify-send to notify when available in the clipboard, 0 = Ignore clipboard action
```

## Usage

`chmod +X droplr`. Then simply add a start script pointing to `droplr` script or run directly to start watching.
