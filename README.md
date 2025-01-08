## commands-notes
-  # sudo systemctl daemon-reload: 
       Reloads the systemd manager configuration.
  This command is used when you modify any systemd unit files, so the systemd service manager is aware of the changes.

  
- # sudo systemctl start myapp.service
       Starts the service.
  It starts the service specified in the unit file (in this case, myapp.service).

- # sudo systemctl status [service_name]
       Shows the status of a service.
  This command displays the current status (running, stopped, failed, etc.) of the specified service.

- # sudo journalctl -u myapp.service -n 50
       Displays the last 50 log entries for the service.
  It fetches the most recent 50 logs from the myapp.service, helpful for troubleshooting.

- # docker build -t [image-name] -f [Dockerfile path] .
         Builds a Docker image from a Dockerfile.
  This command creates a Docker image using the specified Dockerfile (from the path provided) and tags it with the given image name.

- # docker run -d --name [container-name] -p 5000:5000 [image-name]
         Runs a Docker container from an image.
  This runs the Docker container in detached mode (-d), assigns it a name ([container-name]), maps port 5000 from the container to port 5000 on the host, and specifies the image to use ([image-name]).
