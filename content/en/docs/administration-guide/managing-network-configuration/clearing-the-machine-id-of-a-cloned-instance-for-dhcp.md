---
title:  Clearing the Machine ID of a Cloned Instance for DHCP
weight: 9
---

Photon OS uses the contents of `/etc/machine-id` to determine the DHCP unique identifier (duid) that is used for DHCP requests. If you use a Photon OS instance as the base system for cloning, to create additional Photon OS instances, you must clear the `machine-id` with this command: 

    echo -n > /etc/machine-id

When the value is cleared, `machine-id` can be regenerated by calling `systemd-machine-id-setup`. 

    systemd-machine-id-setup
    
This command initializes the machine ID stored in `/etc/machine-id` during installation. For more information on this command, see [https://www.freedesktop.org/software/systemd/man/systemd-machine-id-setup.html](https://www.freedesktop.org/software/systemd/man/systemd-machine-id-setup.html).