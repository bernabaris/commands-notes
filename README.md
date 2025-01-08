# commands-notes
- sudo systemctl daemon-reload
- sudo systemctl start myapp.service
- sudo systemctl status [service_name]
- sudo journalctl -u myapp.service -n 50
- docker build -t [image-name] -f [Dockerfile path] .
- docker run -d --name [container-name] -p 5000:5000 [image-name]
