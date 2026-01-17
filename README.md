# 🛠️ Linux SysAdmin Cheat Sheet

Essential commands for managing High-Performance WordPress Servers on Google Cloud, AWS, and DigitalOcean.

---

## 🔄 Service Management
Quick commands to restart services after configuration changes.

### Nginx Web Server
```bash
# Check Status
sudo systemctl status nginx

# Restart Nginx
sudo systemctl restart nginx

# Test Configuration (Run this before restarting!)
sudo nginx -t

MySQL / MariaDB
# Check Database Status
sudo systemctl status mariadb

# Restart Database Service
sudo systemctl restart mariadb

PHP-FPM
# Check Status
sudo systemctl status php8.1-fpm

# Restart PHP Process Manager
sudo systemctl restart php8.1-fpm

📈 Server Monitoring
Check server health, CPU, RAM, and Disk usage.
# Interactive Process Viewer (CPU/RAM)
htop

# Check Disk Space Usage
df -h

# Check Memory (RAM) Usage
free -m

🕵️‍♂️ Troubleshooting Logs
If a website crashes, check these logs first to find the error.
# Nginx Error Log (Live View)
sudo tail -f /var/log/nginx/error.log

# Nginx Access Log
sudo tail -f /var/log/nginx/access.log

# PHP Error Log
sudo tail -f /var/log/php8.1-fpm.log

🔐 File Permissions (WordPress)
Standard permissions to fix "Permission Denied" errors.
# Set Ownership to Web Server
sudo chown -R www-data:www-data /var/www/html

# Set Directory Permissions
sudo find /var/www/html -type d -exec chmod 755 {} \;

# Set File Permissions
sudo find /var/www/html -type f -exec chmod 644 {} \;

📝 Note
These commands are for Ubuntu/Debian Linux servers. Always backup your configurations before making changes.
