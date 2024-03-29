# iterm2-zmodem
Convenient upload and download file operations with the linux server in MacOS.

Fork from https://github.com/mmastrac/iterm2-zmodem
[Warning] This link is useless.

# Installation

## Prerequisite
- brew
- iterm2
install iterm2 with brew:
```bash
brew cask install iterm2
```

## Step

install lrzsz:
```bash
brew install lrzsz
```

Download `iterm2-send-zmodem.sh` and `iterm2-recv-zmodem.sh`:
```bash
wget https://raw.githubusercontent.com/xmvper/iterm2-zmodem/master/iterm2-send-zmodem.sh

wget https://raw.githubusercontent.com/xmvper/iterm2-zmodem/master/iterm2-recv-zmodem.sh
```

move to `/usr/local/bin/`:
```bash
mv iterm2-send-zmodem.sh iterm2-recv-zmodem.sh /usr/local/bin/
```

change permission:
```bash
cd /usr/local/bin/
chmod 777 /usr/local/bin/iterm2-*
```

set iterm2 in `profiles - default - editProfiles - Advanced`, add two triggers:
```
Regular expression: rz waiting to receive.\*\*B0100
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-send-zmodem.sh
Instant: checked
```
```
Regular expression: \*\*B00000000000000
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
Instant: checked
```


