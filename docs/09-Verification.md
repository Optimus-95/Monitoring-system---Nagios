## Verification

#Verify Nagios Configuration
```bash
sudo /opt/nagios/bin/nagios -v /etc/nagios/nagios.cfg
```
# Check Nagios
```bash
sudo systemctl status nagios
```

# Check NRPE
```bash
sudo systemctl status nrpe
```
# Check PHP-FPM
```bash
sudo systemctl status php8.3-fpm
```
# Verify PHP Port
```bash
sudo ss -tulpn | grep 9000
```
# Reload Nginx
```bash
sudo nginx -s reload
```
