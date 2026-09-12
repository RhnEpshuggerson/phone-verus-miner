# My ccminer setup (Termux on my phone)

## First time setup

1. Install Termux (arm64): https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk

2. Open Termux and run:
```
yes | pkg update -y
yes | pkg upgrade -y
yes | pkg install libjansson wget nano -y
```

3. Download the miner:
```
mkdir ccminer && cd ccminer
wget https://raw.githubusercontent.com/RhnEpshuggerson/phone-verus-miner/main/ccminer
wget https://raw.githubusercontent.com/RhnEpshuggerson/phone-verus-miner/main/config.json
wget https://raw.githubusercontent.com/RhnEpshuggerson/phone-verus-miner/main/start.sh
chmod +x ccminer start.sh
```

## Daily use

Edit pool / address / worker name:
```
nano ~/ccminer/config.json
```
- Pool: `"disabled": 1` = off, `0` = on
- Address + worker name is in `"user"` near the bottom, format: `address.workername`

Start:
```
~/ccminer/start.sh
```

Stop: `CTRL + c`

## Quick tips

- Turn off battery optimization for Termux
- `Acquire wakelock` in the Termux notification = mine with screen off (works on some devices only)
- Hashrate takes ~30 min to 1 h to stabilize
