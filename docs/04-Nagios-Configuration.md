# Nagios Configuration

## Start Nagios Service

```bash
sudo systemctl start nagios

sudo systemctl enable nagios

sudo systemctl status nagios
```
# Copy your customized Nagios configuration files into:
```bash
/etc/nagios/
```
# Files:
--nagios.cfg
--commands.cfg
--contacts.cfg
--holidaylist.cfg
--templates.cfg
--timeperiods.cfg
```bash
sudo mv nagios.cfg /etc/nagios/

sudo mv commands.cfg /etc/nagios/

sudo mv contacts.cfg /etc/nagios/

sudo mv holidaylist.cfg /etc/nagios/

sudo mv templates.cfg /etc/nagios/

sudo mv timeperiods.cfg /etc/nagios/
```
# Remove Printer Monitoring
```bash
sudo rm -rf /etc/nagios/objects/printer.cfg
```
# Validate Configuration
```bash
sudo /opt/nagios/bin/nagios -v /etc/nagios/nagios.cfg
```
