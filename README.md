# k8s-radarr

The goal for this is to help me learn Kubernetes in a practical way while also building out some fundamentals of my homelab.  Radarr will function as the core of the Usenet stack.

# Goal
To setup a deployment of Radarr, accessible via http://<cluster>/radarr as easily as possible.

# How it works
I'm using the NFS-CSI provider to setup the StorageClass for my kstorage1 node, which has a single SSD connected to it.  This is temporary until I complete my NAS setup.

There are 5 PersistentVolumes setup
/movies - holds all the movies
/config - config files for radarr
/downloads - sabnzbd download directory

The Deployment pulls the image from linuxserver, and a Service is setup to establish and endpoint for Radarr.

Finally we have a traefik ingress serving as a reverse proxy, allowing this service to be accessible via http://<node>/radarr/
