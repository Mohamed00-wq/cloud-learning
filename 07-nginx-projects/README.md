# 🌍 Deploy a Static Website with Nginx

## Commands Learned
- `ssh` — remote access
- `scp` — secure file copy
- `rsync` — directory sync
- `chown` / `chgrp` / `chmod` — permissions
- `grep` / `sed` / `awk` / `cut` / `wc` / `sort` — text processing

## Steps

### 1. Install Nginx
```bash
ssh theriepperjohn@127.0.0.1 -p 2222
sudo apt update && sudo apt install nginx -y
```

### 2. Create Website
```bash
sudo mkdir -p /var/www/mysite
echo "<h1>Hello Cloud</h1>" | sudo tee /var/www/mysite/index.html
```

### 3. Set Permissions
```bash
sudo chown -R theriepperjohn:theriepperjohn /var/www/mysite
sudo chgrp -R www-data /var/www/mysite
sudo chmod -R 755 /var/www/mysite
```

### 4. Configure Nginx
```bash
sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/default.bak
sudo sed -i 's|root /var/www/html|root /var/www/mysite|' /etc/nginx/sites-available/default
grep root /etc/nginx/sites-available/default
```

### 5. Restart & Test
```bash
sudo systemctl restart nginx
curl http://localhost
```

### 6. Transfer Files
```bash
scp -P 2222 ~/extra.html theriepperjohn@127.0.0.1:/var/www/mysite/
rsync -avz -e "ssh -p 2222" ~/my-site-files/ theriepperjohn@127.0.0.1:/var/www/mysite/
```

### 7. Analyze Logs
```bash
wc -l /var/log/nginx/access.log
awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -rn
grep ' 200 ' /var/log/nginx/access.log
awk '{print $7}' /var/log/nginx/access.log
```
