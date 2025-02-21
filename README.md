# macOS Essential Applications & Settings



Here is my macOS auto install script. It works on my macOS 12.3 ( Intel x86 CPU )

⚠️⚠️⚠️ 

Base on personal experience, author isn't responsible for any data lost or damage, proceed at your own risk.

⚠️⚠️⚠️


## Install essential package manager & turn off analytics

#### This action needs to typing password manually
  
```
# Install homebrew & Xcode Command Line Tools
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


# Turn off analytics
brew analytics off

```


## Install Rosetta 2 via Command Line on Apple Silicon Mac

#### This action needs to typing password manually
  
```
# Skip the license agreement by providing an additional flag
/usr/sbin/softwareupdate --install-rosetta --agree-to-license

```


## Install CLI Applications

```
brew install \
mackup \
mobile-shell \
mtr \
nmap \
pyenv \
go \
glide \
tmux \
yt-dlp \
git \
tree \
gcc \
autoconf \
automake \
node \
openssl \
byobu \
ffmpeg \
hugo \
google-cloud-sdk \
mas
```



## Install GUI Applications without password

```
brew install \
alfred \
dropbox \
joplin \
google-chrome \
firefox \
visual-studio-code \
bartender \
fantastical \
typinator \
iterm2 \
spotify \
appcleaner \
coderunner \
coconutbattery \
caprine \
transmit \
betterzip \
webpquicklook \
suspicious-package \
divvy \
vlc \
istat-menus \
onyx \
pacifist \
hex-fiend \
1password \
boxcryptor \
little-snitch \
coteditor \
cleanshot \
input-source-pro \
alt-tab \
imazing
```



## Install GUI Applications

#### This area needs to type password manually and change system preferences

```
brew install \
vmware-fusion \
splashtop-personal \
splashtop-streamer \
microsoft-edge \
gpg-suite \
aldente \
maestral \
Veracrypt
```

#### This area needs to use `--cask` to install 

```
brew install --cask \
wireshark \
shimo \
handbrake
```




## Install MAS Applications

#### Sign into the Mac App Store GUI app manually First!

```
mas install APP_ID
```

My Favorite Applications

| APP_ID   | Name                                |
| :------- | :---------------------------------- |
|638161122 |YubiKey Personalization Tool         |
|425264550 |Blackmagic Disk Speed Test           |
|539883307 |LINE                                 |
|1480068668 |Messenger                           |
|409183694 |Keynote                              |
|419330170 |Moom                                 |
|747648890 |Telegram                             |
|425424353 |The Unarchiver                       |
|407963104 |Pixelmator                           |
|409203825 |Numbers                              |
|409201541 |Pages                                |
|1037126344 |Apple Configurator 2                |
|1295203466 |Microsoft Remote Desktop            |
|803453959  |Slack                               |
|1055511498 |Day One                             |
|1230249825 |VMware Remote Console               |
|1464122853 | NextDNS                            |
|1183407767 |MWeb                                |
|497799835 |Xcode                                |



## System Settings

```
# Set a shorter Delay until key repeat		
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 2

# Disable window animations ("new window" scale effect)
defaults write NSGlobalDomain NSAutomaticWindowAnimationsEnabled -bool false

# Use plain text mode for new TextEdit documents
defaults write com.apple.TextEdit RichText -int 0

# Expand save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true

# Check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# Show Path bar in Finder
defaults write com.apple.finder ShowPathbar -bool true

# Show Status bar in Finder
defaults write com.apple.finder ShowStatusBar -bool true

# Show icons for hard drives, servers, and removable media on the desktop
defaults write com.apple.finder.plist ShowExternalHardDrivesOnDesktop 1 && \
defaults write com.apple.finder.plist ShowHardDrivesOnDesktop 1 && \
defaults write com.apple.finder.plist ShowMountedServersOnDesktop 1 && \
defaults write com.apple.finder.plist ShowRemovableMediaOnDesktop 1

# Hide tags in Finder sidebar
defaults write com.apple.finder.plist ShowRecentTags 0

# Avoid creating .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# Enable the Develop menu and the Web Inspector in Safari
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true && \
defaults write com.apple.Safari IncludeDevelopMenu -bool true && \
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true && \
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true && \
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Show absolute path in finder's title bar
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

# Show build duration for Xcode
defaults write com.apple.dt.Xcode ShowBuildOperationDuration YES

# Show system icon in Apple title bar
defaults write com.apple.systemuiserver menuExtras -array \
"/System/Library/CoreServices/Menu Extras/Bluetooth.menu" \
"/System/Library/CoreServices/Menu Extras/Clock.menu" \
"/System/Library/CoreServices/Menu Extras/AirPort.menu" \
"/System/Library/CoreServices/Menu Extras/Battery.menu" \
"/System/Library/CoreServices/Menu Extras/TimeMachine.menu" \
"/System/Library/CoreServices/Menu Extras/Displays.menu" \
"/System/Library/CoreServices/Menu Extras/VPN.menu" \
"/System/Library/CoreServices/Menu Extras/User.menu" \
"/System/Library/CoreServices/Menu Extras/WWAN.menu" \
"/System/Library/CoreServices/Menu Extras/Volume.menu"

# Restart System UI Service
killall SystemUIServer
```


## Others

#### Install oh-my-zsh (typing password manually)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
sed -i -e 's/robbyrussell/agnoster/g' ~/.zshrc
rm ~/.zshrc-e
```

[Reference](https://iphone4.tw/forums/showthread.php?t=206652)



#### Manage favorite items & location in Finder sidebar

```
cp ./{com.apple.LSSharedFileList.FavoriteItems.sfl2,com.apple.LSSharedFileList.FavoriteVolumes.sfl2} ~/Library/Application\ Support/com.apple.sharedfilelist/
```

[Reference](https://apple.stackexchange.com/questions/366856/use-profile-manager-or-other-methods-for-network-mounts-favorites)


#### Install Fonts

```
brew tap homebrew/cask-fonts

brew install \
font-anonymous-pro \
font-fira-code \
font-hack \
font-source-code-pro \
font-menlo-for-powerline
```



## Setup Hostname (Be sure to change hostname to yours)

```
sudo scutil --set HostName emp
```

## Enable Touch ID for sudo Authentication in Terminal

```
sudo sed -i ".bak" '2s/^/auth       sufficient     pam_tid.so\'$'\n/g' /etc/pam.d/sudo
```

Workaround for iTerm2: Turn off `Prefs > Advanced > Allow sessions to survive logging out and back in`


## Block & Re-Enable updates to macOS Catalina 10.15

```
# For Block
sudo softwareupdate --ignore "macOS Catalina"
```
```
# Remove Update Notification
defaults delete com.apple.preferences.softwareupdate LatestMajorOSSeenByUserBundleIdentifier && softwareupdate --list
```

```
# For Re-Enable
sudo softwareupdate --reset-ignored
```

## Disable Gatekeeper in macOS Sierra or later

⚠️⚠️⚠️ Proceed at your own risk ⚠️⚠️⚠️
```
sudo spctl --master-disable
```

## Restart Touchbar Service

```
sudo pkill TouchBarServer
```


## Manually Install

* [iPhone Backup Extractor](https://www.iphonebackupextractor.com/)
* [Python 2.7.18](https://www.python.org/downloads/release/python-2718/)


## Useful Tools & Links

* [fetch-installer-pkg](https://github.com/scriptingosx/fetch-installer-pkg)
* [Kerberos for macOS](https://computing.help.inf.ed.ac.uk/kerberos-mac-os-x)
* [Bash Keystrokes – Mosky’s Notes](https://paper.dropbox.com/doc/Bash-Keystrokes-Moskys-Notes-jc4OF7EoXcOIuA9gtPs13)



## My favorite Apps in SetApp

<img src="https://i.imgur.com/KUtMXor.png)" style="zoom:50%" />

