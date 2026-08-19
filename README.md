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
