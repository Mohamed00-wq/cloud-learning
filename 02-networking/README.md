# 🌐 Networking & HTTP Verification

## Inspect Network Interfaces
```bash
ip a
```
Two important addresses:
- `127.0.0.1` — loopback (localhost)
- `10.0.2.15` — VM's private IP via VirtualBox NAT

## Inspect the Routing Table
```bash
ip route show
```

## Check Listening Ports
```bash
sudo ss -tlnp
ss -tuln
sudo ss -tlnp | grep 80
```

## Test Internet Connectivity
```bash
ping -c 4 8.8.8.8   # test by IP
ping -c 4 google.com # test DNS resolution
```

## Download a Web Page
```bash
wget http://localhost
```

## Inspect HTTP Headers
```bash
curl -I http://localhost
```

## Check HTTP Status Code
```bash
curl -s -o /dev/null -w "%{http_code}\n" http://localhost
```

| Code | Meaning |
|------|---------|
| 200 | Success |
| 404 | Not Found |
| 500 | Server Error |
