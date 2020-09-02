# bluetooth-audio
A bash script to auto-select a specified bluetooth audio device when connected.

To install as a systemd user service:

Add script to location of choice:
e.g
```bash 
mv bluetooth-audio /usr/local/bin
```

Note: ensure ```ExecStart``` in ```bluetooth-audio@.service``` matches the chosen location

Add unit file to systemd user directory
```bash 
mv bluetooth-audio@.service ~/.config/systemd/user
```

Find MAC address of bluetooth device: 
```bash 
bluetoothctl info
```

Using the user service:

```bash 
systemctl enable|start|stop|disable --user bluetooth-audio@"<DEVICE_MAC_ADRESS>".service
```
