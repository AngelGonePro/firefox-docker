https://raw.githubusercontent.com/AngelGonePro/firefox-docker/refs/heads/main/firefox-container.zip
```
rm -rf ~/firefox-container && \
mkdir -p ~/firefox-container && \
wget -q -O /tmp/firefox-container.zip https://raw.githubusercontent.com/AngelGonePro/firefox-docker/refs/heads/main/firefox-container.zip && \
unzip -q /tmp/firefox-container.zip -d ~ && \
rm /tmp/firefox-container.zip && \
cd ~/firefox-container && \
ls -la
```
```
server {
    listen 80;
    server_name browsetheweb.cosmoscraft.net;

    real_ip_header CF-Connecting-IP;

    client_max_body_size 100M;

    location / {
        proxy_pass https://10.0.0.50:5800;
        proxy_ssl_verify off;
        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto https;

        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";

        proxy_buffering off;
        proxy_read_timeout 3600;
        proxy_send_timeout 3600;
    }
}
```
