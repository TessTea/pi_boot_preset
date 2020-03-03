# Botstrap Raspberry Pi as single-node K8S cluster with Flannel CNI

## How can i use it:
- Flash SD card with raspbian lite
- Substitute fields "ssid" & "psk" with your current wifi parameters
- Copy files "ssh" and "wpa_supplicant.conf" to the root of /boot partition on your SD-card
- Remove card, plug it into your RPi 3B+ or higher and power it on
- Give it 30 seconds to boot
- Then from machine in same wi-fi network try to ping reaspberrypi.local
- It should be available
- `ssh pi@raspberypi.local "bash -s" < cluster_shortcut`
- `Make a cut of tea and wait till it finished
- When it's done, try to login with login/pass tess/kjkszpj
- Check cluster state: `kubecl get pods -n kube-system`
- It sould looks like that:
```
NAME                                  READY   STATUS    RESTARTS   AGE
coredns-6955765f44-mhfbs              1/1     Running   0          12m
coredns-6955765f44-nvdd8              1/1     Running   0          12m
etcd-raspberrypi                      1/1     Running   1          12m
kube-apiserver-raspberrypi            1/1     Running   1          12m
kube-controller-manager-raspberrypi   1/1     Running   3          12m
kube-flannel-ds-arm-lfc8r             1/1     Running   0          12m
kube-proxy-sr5d6                      1/1     Running   0          12m
kube-scheduler-raspberrypi            1/1     Running   2          12m
```
- Now do,what you want to do with it
