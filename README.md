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
