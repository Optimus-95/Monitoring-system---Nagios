# Nagios Plugins

## Install Custom Theme

Extract Theme

```bash
tar -xf vautour-style.tar.gz

cd vautour-style/
```
# Copy Theme
```bash
sudo cp -r * /opt/nagios/share/
```
Set Ownership
```bash
sudo chown nagios /opt/nagios/share/

sudo chown -R nagios /etc/nagios

sudo chown -R nagios /opt/nagios
```
# Install Nagios Plugins
Extract
```bash
tar -xf nagios-plugins.tar.gz
cd nagios-plugins-2.4.12/
```
Configure
```bash
./configure \
--prefix=/opt/nagios \
--libexecdir=/opt/nagios/libexec \
--sysconfdir=/etc/nagios \
--datadir=/opt/nagios/share \
--enable-extra-opts \
--with-nagios-user=nagios \
--with-nagios-group=nagios \
--localstatedir=/var/nagios 
```
Compile
```bash
make -j12
```
Install
```bash
sudo make install
```
Permissions
```bash
sudo chmod 755 /opt/nagios/libexec/*
sudo chown -R nagios:nagios /opt/nagios/libexec*
```
Deploy Custom Plugins
```bash
tar -xf libexec2.tar

sudo cp -r libexec2 /opt/nagios/

sudo chmod 755 /opt/nagios/libexec2/*

sudo chown -R nagios:nagios /opt/nagios/libexec2*

sudo systemctl restart nagios
```
