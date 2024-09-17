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
