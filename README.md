# dockeros
My Experimentation with Docker

I host a domain as a hobby and like to experiment...
Currently I use Docker Ubuntu 22.04 VirtualBox VM in Windows. I tried to use Docker in WSL but I gave up quickly due to network configure difficulties... Maybe some day I'll set up a dedicated Linux machine to host these services.

Generally I try to run Docker containers as other than root UID:GID because I want to access the data (Backed up images, TVH recordings etc.) from Windows using VirtualBox Shared Folder functionality. This introduces some ownership problems... If a docker image uses other UID:GID, data needs to be stored inside VM filesystem, which makes it more cumbersome to access.

## [WatchTower](https://github.com/containrrr/watchtower)

Keeps all docker images up to date
- [watchtower](watchtower)

***

## [TVHeadEnd](https://github.com/linuxserver/docker-tvheadend)

Records my favourite TV shows with HDHomeRun DVB tuner.
- [tvheadend](tvheadend)

***

## [NGINX reverse proxy](https://github.com/nginx-proxy/nginx-proxy) with [ACME companion](https://github.com/nginx-proxy/acme-companion)

Automatic SSL certificate creation for domains
- [nginx-proxy](nginx-proxy)

Following services are placed behind NGINX reverse proxy network:

### [NextCloud](https://github.com/nextcloud/docker)
Private cloud with automatic backup of images from phone
- [nextcloud](nextcloud)

***

In order to use GMail account to send e-mail notifications from NextCloud and WatchTower, [Google App Passwords](https://support.google.com/accounts/answer/185833) needs to be created.
