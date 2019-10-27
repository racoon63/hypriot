# hypriot

General purpose repository for hypriot notes and files.

## Flash SDcard

To flash your SD card, it is recommended to use the flash tool from the hypriot developers.

[Hypriot Flash Tool](https://github.com/hypriot/flash)

I would also recommend to provide a cloud-config file for cloud-init. You will find the documentation [here](https://cloudinit.readthedocs.io/en/latest/). You can find an example [here](https://github.com/racoon63/hypriot/cloud-init/cloud-config.example.yaml).

## Confirguration

When you want to reconfigure your hypriot host, you have to login your hypriot host and go to `/var/lib/cloud/`. In this directory there are the configuration files of your hypriot hosts. The configuration is stored permanently in these. People reported that their configurations like hostname, locales etc. are not saved permanently. When you change them in here, they are permanent even after rebooting your host.
