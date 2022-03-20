# Self-signed certificate

## Usage
```
openssl req -x509 -nodes -days 365 -newkey rsa:4096 -keyout /etc/ssl/private/selfsigned.key -out /etc/ssl/certs/selfsigned.crt
```

### Apache Configuration
```
	SSLCertificateFile /etc/ssl/certs/selfsigned.crt
	SSLCertificateKeyFile /etc/ssl/private/selfsigned.key
```
## Notes
- Don't use more than `-days 365`, *it's bad for SSL!*