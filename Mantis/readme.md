# Mantis

## Linux Service File

`/etc/systemd/system/mantis.service`

```
[Unit]
Description=Mantis client service file
After=network.target

[Service]
ExecStart=/home/stev/mantis/bin/mantis-launcher etc -Dmantis.datadir=/home/stev/.mantisDatdir

[Install]
WantedBy=default.target
```

### Usage

```
systemctl status mantis
systemctl start mantis
systemctl stop mantis
```

Default RPC endpoint http://127.0.0.1:8546