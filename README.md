# WSDCF Decrypt

A tiny Windows tool that converts DMM / FANZA `.wsdcf` video files into plain
`.mp4`, so you can play your purchased content in any player or on any device
(VR headsets, Plex, VLC, etc.).

> **Personal use only.** Use it only on content you have legally purchased or
> rented. Do not redistribute decrypted content.

## Requirements

- **Windows** (the tool is a Windows executable).
- **DMM VR Player** installed (it is used to authorize playback).
- A **DMM / FANZA account** that owns the content, signed in to the DMM VR
  Player at least once (so the player stores your login).

## Setup

1. Download `WsdcfDecrypt.exe` from this repository.
2. That's it — no installer, no dependencies.

## Usage

Open a Command Prompt and run:

```
WsdcfDecrypt.exe "path\to\video.wsdcf" "path\to\output.mp4"
```

Examples:

```
WsdcfDecrypt.exe "C:\Videos\movie.wsdcf" "C:\Videos\movie.mp4"
```

The tool automatically:

- finds your DMM VR Player installation,
- uses your saved DMM login,
- acquires the playback license (even if you never opened the file in the
  player),
- writes a decrypted `.mp4`.

## Decrypt a whole folder

From a Command Prompt, use a `for` loop:

```
for %f in ("C:\path\to\folder\*.wsdcf") do WsdcfDecrypt.exe "%f" "%~dpnf.mp4"
```

(In a batch `.bat` file, double the percent signs: `%%f` and `%%~dpnf`.)

## Notes

- Files you already opened in the DMM VR Player decrypt instantly; new files
  need a brief network call to fetch the license.
- The tool runs entirely on your machine.

---

Developed with assistance from DeepSeek.
