#####USER ######
###add a non sudo user
On Fedora / RHEL systems (using useradd):
sudo useradd -m -s /bin/bash user
sudo passwd user

(Optional) Enable lingering (so user services run even if not logged in)
sudo loginctl enable-linger mediauser

when using podman on non root, publish port is not auto, on your sudo account

#### PORTS ######
eg for jellyfin
sudo firewall-cmd --add-port=8096/tcp --permanent
