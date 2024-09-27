This project allows you to download music from Spotify, whether that be a song, album, or playlist. I am using this for my project. The information below helps users to install the needed software so that they can begin downloading their favorite songs.

<a href="https://github.com/spotDL/spotify-downloader"><img align="right" src="static/logo-transparent.png" alt="logo" width="253" height="116"/></a>
# spotDL

> **The fastest, easiest, and most accurate command-line music downloader**

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/spotDL/spotify-downloader/blob/master/LICENSE)
![Contributors](https://img.shields.io/github/contributors/spotDL/spotify-downloader)
![downloads](https://img.shields.io/github/downloads/spotDL/spotify-downloader/latest/total)
[![BCH compliance](https://bettercodehub.com/edge/badge/spotDL/spotify-downloader?branch=master)](https://bettercodehub.com/)
[![pypi version](https://img.shields.io/pypi/pyversions/spotDL)](https://pypi.org/project/spotdl/)
[![pypi version](https://img.shields.io/pypi/v/spotDL)](https://pypi.org/project/spotdl/)
[![pypi downloads](https://img.shields.io/pypi/dw/spotDL?label=downloads@pypi)](https://pypi.org/project/spotdl/)
[![Discord](https://img.shields.io/discord/771628785447337985.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.gg/xCa23pwJWY)
![GitHub commits since latest release (by date)](https://img.shields.io/github/commits-since/spotDL/spotify-downloader/latest)


What spotDL does:

1. Downloads music from Spotify as an MP3 file
2. Applies basic metadata gathered from Spotify such as:
   - Track Name
   - Track Number
   - Album
   - Album Cover
   - Genre
   - and more!


## Installation

You need to download FFmpeg to use this tool. Download and installation instructions can be found at [FFmpeg.org](https://ffmpeg.org/)

### Installing spotDL

- Recommended Stable Version:

  ```
  $ pip install spotdl
  ```

- Install directly from master: (Use if experiencing issues)

  ```
  $ pip install https://codeload.github.com/spotDL/spotify-downloader/zip/master
  ```

- Dev Version: __(NOT STABLE)__

  ```
  $ pip install https://codeload.github.com/spotDL/spotify-downloader/zip/dev
  ```

#### On Termux:
  
  ```
  curl -L https://github.com/spotDL/spotify-downloader/raw/master/termux/setup_spotdl.sh | sh
  ```

## Usage (Instructions for v3)

- To download a song, run:

  ```
  $ spotdl [trackUrl]
  ```

  ex. `spotdl https://open.spotify.com/track/0VjIjW4GlUZAMYd2vXMi3b?si=1stnMF5GSdClnIEARnJiiQ`


- To download an album, run:

  ```
  $ spotdl [albumUrl]
  ```

  ex. `spotdl https://open.spotify.com/album/4yP0hdKOZPNshxUOjY0cZj?si=AssgQQrVTJqptFe7X92jNg`


- To download a playlist, run:

  ```
  $ spotdl [playlistUrl]
  ```

  ex. `spotdl https://open.spotify.com/playlist/37i9dQZF1E8UXBoz02kGID?si=oGd5ctlyQ0qblj_bL6WWow`


- To search for and download a song, run, __with quotation marks__:  
  _Note: This is not accurate and often causes errors._

  ```
  $ spotdl '[songQuery]'
  ```

  ex. `spotdl 'The Weeknd - Blinding Lights'`


- To resume a failed/incomplete download, run:

  ```
  $ spotdl [pathToTrackingFile]
  ```

  ex. `spotdl 'The Weeknd - Blinding Lights.spotdlTrackingFile'`

  _`.spotdlTrackingFile`s are automatically created when a download starts and deleted on completion_


You can queue up multiple download tasks by separating the arguments with spaces:

```
$ spotdl [songQuery1] [albumUrl] [songQuery2] ... (order does not matter)
```

ex. `spotdl 'The Weeknd - Blinding Lights' https://open.spotify.com/playlist/37i9dQZF1E8UXBoz02kGID?si=oGd5ctlyQ0qblj_bL6WWow ...`


_spotDL downloads up to 4 songs in parallel, so for a faster experience, download albums and playlist, rather than tracks._

## `pipx` Isolated Environment Alternative

For users who are not familiar with `pipx`, it can be used to run scripts __without__ installing the spotDL package and all the dependencies globally with pip. (Effectively skipping over the [Installation](https://github.com/spotDL/spotify-downloader#Installation) step)

First, you will need to install `pipx` by running:

```
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Next, you can jump directly to running spotDL with:

```
pipx run spotdl ...
```

An example for how to use the pipx run spotdl command would be like this:

pipx run spotdl 'https://open.spotify.com/track/6y4GYuZszeXNOXuBFsJlos?si=CSBVqMpPSciX8wt7eLXdJw'
