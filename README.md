```
kubesvcexporter.service
[Unit]
Description=KubeSvcExporter Service
After=network.target

[Service]
ExecStart=/usr/local/bin/kubesvc/kubesvc_exporter -auth /usr/local/bin/kubesvc/auth.txt -port 8090 -url /usr/local/bin/kubesvc/url.txt -timeout 1000
Restart=always
User=root
Group=root

[Install]
WantedBy=multi-user.target

auth.txt
username:password

url.txt
http://svcIP:svcPORT svcName
```
