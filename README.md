# Passwordless `sudo`
```bash
sudo visudo
```
Add to the end of the file:
```
tim ALL=(ALL) NOPASSWD: ALL
```

# fish shell
```bash
sudo apt-add-repository ppa:fish-shell/release-2
sudo apt-get update
sudo apt-get install fish
chsh -s /usr/bin/fish
```

# Google Chrome
1. Open Firefox
2. www.google.com/chrome
3. Download .deb
4. `sudo dpkg -i ~/Downloads/google-chrome-stable_current_amd64.deb`
5. `sudo apt --fix-broken install`

# Terminator
```bash
sudo apt-get install terminator
```
