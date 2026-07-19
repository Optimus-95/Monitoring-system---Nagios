# PHP-FPM Configuration

## Edit Pool Configuration

```bash
vi /etc/php/8.3/fpm/pool.d/www.conf
```
# Update
listen = 127.0.0.1:9000

# Comment
#listen = /run/php/php8.3-fpm.sock

# Restart
```bash
sudo systemctl restart php8.3-fpm
```

# Verify
```bash
sudo ss -tulpn | grep 9000
```
