# NRPE Installation

## Extract Source

```bash
tar -xf nrpe-4.1.0.tar.gz

cd nrpe-4.1.0
Configure
sudo ./configure \
--prefix=/opt/nagios \
--libexecdir=/opt/nagios/libexec \
--datadir=/opt/nagios/share \
--sysconfdir=/etc/nagios \
--enable-command-args \
--with-nrpe-user=nagios \
--with-nrpe-group=nagios \
--with-nagios-user=nagios \
--with-nagios-group=nagios \
--disable-ssl
```

# Compile
```bash
make all
```

# Install
```bash
sudo make install-groups-users

sudo make install-config

sudo make install-init

sudo make install
```
# Enable Service
```bash
sudo systemctl start nrpe

sudo systemctl enable nrpe
```
# Configure NRPE

Edit
```bash
sudo vi /etc/nagios/nrpe.cfg
```

# Update
allowed_hosts=127.0.0.1,<Host-IP>

dont_blame_nrpe=1

allowed_hosts=127.0.0.1,<Host-IP>

dont_blame_nrpe=1
