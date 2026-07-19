# Nagios Core Installation

## Download and Extract Source Package

```bash
tar -xf nagios-4.5.10.tar.gz

cd nagios-4.5.10/
```

# Configure Nagios
```bash
sudo ./configure \
--prefix=/opt/nagios \
--libexecdir=/opt/nagios/libexec \
--sysconfdir=/etc/nagios \
--with-nagios-user=nagios \
--with-nagios-group=nagios \
--enable-nanosleep \
--enable-event-broker \
--enable-embedded-perl \
--enable-perl-modules \
--with-gnutls \
--with-openssl \
--with-mail=/usr/bin/mailx \
--datadir=/opt/nagios/share \
--localstatedir=/var/nagios \
--with-httpd-conf=/etc/nginx/conf.d/
```
# Install Nagios
```bash
sudo make all

sudo make install-groups-users

sudo usermod -a -G nagios nginx

sudo make install

sudo make install-daemoninit

sudo make install-commandmode

sudo make install-config

sudo make install-webconf

sudo make install-exfoliation
```
