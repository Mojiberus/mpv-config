# mpv-config

My mpv configuration w/ files.
This repo contains my files and configs for mpv and its additions.

## Getting Started

First, you need to have mpv installed. Download it at https://mpv.io and install it.

## Downloading files

Download `portable_config.7z` and extract its files to `mpv-XXXXXX/portable_config` where XXXXXX is your mpv folder with `mpv.exe` itself. If you don't have it - make one.

Now it should look like this.

![Result](https://github.com/Mojiberus/mpv-config/blob/edde119184becc25c85df1c2c1b5c383b0b1b3c4/screenshots/Screenshot%202022-06-07%20231458.jpg)

# That's it!

Now you have the same mpv setup as mine, with my keybinds, shaders, scripts and their configs.

Now you need to configure some files.

## Configuration

### Set up mpv.conf

Open `portable_config/mpv.conf` with text editor like VSC/VS/NP++.

`keep-open=always` will keep mpv open after you reach the end of video.

`script-opts-append=ytdl_hook-ytdl_path=yt-dlp` is for yt-dlp to watch online videos in mpv supported by yt-dlp.

If you don't need it, remove the line. If you need it, check yt-dlp+mpv installation.

`gpu-api=` controls which type of graphics APIs will be accepted. You need to pick one of these: `auto` `opengl` `vulkan` `d3d11`.

Now pay attention to `hwdec` and `hwdec=auto` lines. You might need to configure them according to https://mpv.io/manual/stable/#options-hwdec. If you're not sure what are you setting up here, leave it as I set up.

`volume=80` sets default audio volume to 80 when you open a video. Use any value you prefer.

`screenshot-template=` tells mpv how screenshot should be named when you take it with s/S. Refer to https://mpv.io/manual/stable/#options-screenshot-template to set it up as you need.

`screenshot-directory='C:\Users\Mojiberus\Pictures\mpv'` tells mpv where screenshots should be saved after taking. Set it up to your own folder or remove it to automatically save screenshots on your desktop.

`screeshot-format=png` use .png file format for screenshots you take. Pick one of these: `png` `jpg` `jpeg` `webp`.

`sub-file-paths="C:\Users\Mojiberus\Videos\**"` is used with `fuzzydir` script, which will recursively load subs from subfolders where video is placed.

Set it up to your folder where you store videos with subs.

For example, if you have a video named `Episode 1.mp4` and a folder with any name, which contains a file named `Episode 1.ass`, you will be able to access subtitles for a video without drag-and-dropping .ass file into mpv window.

### Set up input.conf

The first thing you should learn are default keybinds for mpv. Default keybinds are stored in `mpv-XXXXXX/doc/mpbindings.png` which is brief overview. Full list of kenbinds. 

Keybinds which are set in `input.conf` will override their respective default.

My `input.conf` contains a duplicate for ru-RU layout. 

Keybinds are case and input layout sensitive. That means pressing `w` won't do the same as `W`, `ц` or `Ц` if of course you didn't set them to same action.

If you have layouts other than en-US and ru-RU, then you need to make a copy of `ru-RU Layout fix + my kenbinds`, paste it and replace all ru-RU keybinds with your layout.

## Now I'll explain what my keybinds do

`Right` will fast-forward 5 seconds, and `Left` will rewind 5 seconds.

`Alt+Right` will step 1 frame forward, and `Alt+Left` will do backwards.

`b`/`и` will turn off borders.

`Q`/`Й` will close the windows, and `q`/`й` will close with watch-later option.

`Keypad 4` will switch to next video in the folder, and `Keypad 6` to previous. These keybinds are used with `autoload.lua` script.

`Keypad 8` will turn off borders and turn on stay-on-top, like PiP in browsers.

`Keypad 2` will restart video.

`End` will fast-forward 90 seconds. Useful to skip anime OP.

#### Anime4K

These keybinds are used to increase video quality using Anime4K shaders. As it comes from the name, it's for anime. 

These keybinds are for low-end GPUs. If you have a high-end GPU, then replace them with https://github.com/bloc97/Anime4K/blob/master/md/GLSL_Instructions_Windows.md#optimized-shaders-for-higher-end-gpu.

`Ctrl+1~6` will switch between modes. Each has different delay and effect.

`Ctrl+0` will disable applied shaders.

# Good job!

You made your mpv build based on mine. 

I will update `mpv.conf` and `input.conf` separately from `portable_config.7z` when I change them. 
