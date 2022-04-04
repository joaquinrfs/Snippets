# Wait for Network service
Common issue with Ubuntu Server, may be common as well in other distros:
```
A start job is running for Wait for Network to be Configured (Xmin Ys / no limit)
```

# Solutions

## Make it optional
You can tell the system that the network interface is optional.

1. Add `optional: true` to `/etc/netplan/00-installer-config.yaml or 01-netcfg.yaml`.
2. Restart the service with `netplan apply`.

### Notes
- Use *2 spaces* for indentation, otherwise netplan will whine about it.

## Disable service
You can just disable the service.

1. Disable the service with `systemctl disable systemd-networkd-wait-online.service`.
2. Prevent it from being re-enabled with `systemctl mask systemd-networkd-wait-online.service`.