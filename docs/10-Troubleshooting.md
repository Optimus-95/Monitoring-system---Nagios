# Troubleshooting

## fcgiwrap Permission Issue

Check Socket
```bash
ls -l /var/run/fcgiwrap.socket
```

Temporary Fix
```bash
sudo chmod 666 /var/run/fcgiwrap.socket

sudo nginx -s reload
```

Permanent Fix
```bash
sudo chmod 660 /var/run/fcgiwrap.socket

sudo usermod -aG www-data nginx

sudo systemctl daemon-reload

sudo systemctl restart fcgiwrap

sudo nginx -s reload
```

Remove Default Objects
```bash
sudo rm -rf windows.cfg switch.cfg

sudo systemctl restart nagios
```
