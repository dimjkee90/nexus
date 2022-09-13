Nexus

Generate ssl for a docker registry
```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -addext "subjectAltName = IP:192.168.1.1" -keyout nexus3.key -out nexus3.crt
```

if you need a DNS name, then
```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -addext "subjectAltName = DNS:domain-name.com" -keyout nexus3.key -out nexus3.crt
```

Make a copy of the .crt file generated earlier, name it ca.crt and place it under /etc/docker/certs.d/192.168.0.17
(replace the name of the last directory in the past with your IP or DNS name)
``` 
mkdir -p /etc/docker/certs.d/192.168.1.1
cp nexus3.crt /etc/docker/certs.d/192.168.1.1/ca.crt
```



