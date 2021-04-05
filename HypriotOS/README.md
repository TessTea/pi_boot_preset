# HypriotOS

Fully-functional lightweight reaspbian-upstream-based image optimized to work with docker.

Have a lot of convenient features to cloud-init.

## Best way to setup server:

### Prepare SD-flasher:

Using [Hypriot-flash](https://github.com/hypriot/flash):

```bash
curl -LO https://github.com/hypriot/flash/releases/download/<current-version>/flash
chmod +x flash
sudo mv flash /usr/local/bin/flash
```

Help-view:

```bash
Flash a local or remote Raspberry Pi SD card image.

OPTIONS:
  --help|-h       Show this message
  --bootconf|-C   Copy this config file to /boot/config.txt
  --config|-c     Copy this config file to /boot/device-init.yaml (or occidentalis.txt)
  --hostname|-n   Set hostname for this SD image
  --ssid|-s       Set WiFi SSID for this SD image
  --password|-p   Set WiFI password for this SD image
  --clusterlab|-l Start Cluster-Lab on boot: true or false
  --device|-d     Card device to flash to (e.g. /dev/sdb in Linux or /dev/disk2 in OSX)
  --force|-f      Force flash without security prompt (for automation)
  --userdata|-u   Copy this cloud-init file to /boot/user-data
  --metadata|-m   Copy this cloud-init file to /boot/meta-data
  --file|-F       Copy this file to /boot

If no image is specified, the script will try to configure an existing
image. This is useful to try several configuration without the need to
rewrite the image every time.

For HypriotOS < v1.7.0:

The config file device-init.yaml should look like

hostname: black-pearl
wifi:
  interfaces:
    wlan0:
      ssid: "MyNetwork"
      password: "secret_password"

For HypriotOS v1.7.0 and higher:

The config file user-data config file is the cloud-init configuration.
See http://cloudinit.readthedocs.io/en/0.7.9/ for more details.
```

### Flash and run your RPi:

0. Write your configuration to the user-data
1. Download prefered verion of [HypriotOS](https://blog.hypriot.com/downloads/)
2. Run `flash -f hypriotos-rpi-v1.12.0.img.zip -u user-data`
3. Insert SD card to your notebook
4. Press RETURN
5. Eject SD card and insert it to your Raspberry Pi - done!
6. Make a cut of tea and wait till it finished seting-up
7. Login with `ssh <user>@<hostname>.local`

