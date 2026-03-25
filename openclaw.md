ssh -N -L 18789:127.0.0.1:18789 pi@192.168.100.103
ssh -N -L 3939:127.0.0.1:3939 pi@192.168.100.103
ssh -N -L 18789:127.0.0.1:18789 pi@192.168.100.103


openclaw agents add Coder --workspace /home/pi/.openclaw/workspace-coder
openclaw agents add coder
openclaw pairing list

openclaw gateway restart