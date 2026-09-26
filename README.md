# VoiceTila for Linux

Packages of [VoiceTila](https://voicetila.layero.app) — dictation and voice commands recognised on
your computer. This repository only hosts the built packages; the source is developed elsewhere.

**Status:** early preview. Recognition, dictation from the window and the tray, and opening
programs, files and websites by voice work. Global hotkeys and automatic insertion into other
apps arrive in the next version.

## Debian, Ubuntu, Linux Mint (x86_64, arm64)

```sh
curl -fsSL https://bantila.github.io/voicetila-linux/voicetila.asc | sudo gpg --dearmor -o /usr/share/keyrings/voicetila.gpg
echo "deb [signed-by=/usr/share/keyrings/voicetila.gpg] https://bantila.github.io/voicetila-linux/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/voicetila.list
sudo apt update && sudo apt install voicetila
```

## Fedora, openSUSE, RHEL (x86_64, aarch64)

```sh
sudo tee /etc/yum.repos.d/voicetila.repo <<'REPO'
[voicetila]
name=VoiceTila
baseurl=https://bantila.github.io/voicetila-linux/rpm/$basearch
enabled=1
gpgcheck=0
repo_gpgcheck=1
gpgkey=https://bantila.github.io/voicetila-linux/voicetila.asc
REPO
sudo dnf install voicetila
```

## Any distribution: AppImage

Download `VoiceTila-<version>-x86_64.AppImage` or `-aarch64.AppImage` from
<https://bantila.github.io/voicetila-linux/>, make it executable and run it.

On first start VoiceTila downloads a speech model (about 310 MB for Russian, 640 MB for 25 languages).
After that it works offline; speech never leaves the computer.
