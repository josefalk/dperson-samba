# dperson-samba



```
docker run -d \
  --name samba_container \
  -p 139:139 -p 445:445 \
  -v /mnt/rec:/mnt/rec \
  -v /mnt:/mnt \
  dperson/samba:latest \
  -p -u 'pi;pi' \
  -s 'rec;/mnt/rec;yes;no;no;pi' \
  -s 'another_share;/mnt;yes;no;no;pi'
```



```
sudo mount -t cifs -o username=pi,password=pi,iocharset=utf8,uid=$(id -u pi),gid=$(id -g pi),file_mode=0777,dir_mode=0777,vers=2.0 "//windowsshare/share" /home/pi/share/
```



```
sudo docker run -d --name=qbittorrent \
  -v /home/pi/m-share/incomplete:/downloads/incomplete \
  -v /home/pi/m-share/done:/downloads/completed/done \
  -e WEBUI_PORT=8080 \
  -e PUID=1000 -e PGID=1000 \
  -e UMASK_SET=022 \
  -p 8080:8080 \
  --restart unless-stopped \
  linuxserver/qbittorrent:4.6.0
```



```
sudo docker cp /home/pi/m-share/torrent-files/* qbittorrent:/downloads/torrent-files/
```
