
[Unit]
Description=Syncthing container
After=local-fs.target

[Service]
# Create the main directories
# Always pull the latest version on boot
ExecStartPre=podman pull docker.io/syncthing/syncthing:latest
Restart=always

[Container]
ContainerName=syncthing
HostName=syncthing
Image=docker.io/syncthing/syncthing:latest
SecurityLabelDisable=true
Environment=PUID=1001
Environment=PGID=1001
Volume=/home/poduser/podman/syncthing:/var/syncthing/config:Z
Volume=/home/poduser/podman/syncthing/cache:/var/syncthing/cache:Z
Volume=/media/hdd1/00SyncPod:/data:z
PublishPort=8384:8384
PublishPort=22000:22000/tcp
PublishPort=22000:22000/udp
PublishPort=21027:21027/udp

[Install]
# Start by default on boot
WantedBy=multi-user.target default.target

-----------------------------------------------------------
#### mightneed 
podman unshare
chown podman/syncthing/

#### chmod -R 777 /media/
