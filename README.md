# hypriot

General purpose repository for hypriot notes and files.

## Flash SDcard

To flash your SD card, it is recommended to use the flash tool from the hypriot developers.

[Hypriot Flash Tool](https://github.com/hypriot/flash)

I would also recommend to provide a cloud-config file for cloud-init. You will find the documentation [here](https://cloudinit.readthedocs.io/en/latest/). You can find an example [here](https://github.com/racoon63/hypriot/cloud-init/cloud-config.example.yaml).

## Configuration

To configure your host, use a cloud-config file.

### Reconfiguration

When you want to reconfigure your hypriot host, you have to login your hypriot host and go to `/boot/`. In this directory there are various configuration files of your hypriot host. The configuration is stored permanently in these. If you want to reconfigure your host then edit `/boot/user-data`, close and save the cloud-config file. Afterwards run:

```bash
sudo cloud-init clean
```

to clean the current config. Use

```bash
sudo cloud-init init
```

to rebuild the config. To apply the config reboot the host with:

```bash
sudo reboot now
```
