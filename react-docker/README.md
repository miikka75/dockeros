# React app in Nginx Docker container

## Execute React app locally

```bash
npm start
```

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.


## Build React app for production

Builds the app for production to the `build` folder.\

```bash
npm run build
```

## Execute React app in a Docker container locally
```bash
docker-compose up -d
```

## Execute React app in a Docker container in remote context

### Prerequisites
Create a remote context. [Example setup with OCI](https://github.com/miikka75/remote-docker)
```bash
docker context create <remote> --docker "host=ssh://<user>@<ip_address_or_hostname>"
```

If you have defined host (for example with User, Hostname and IdentityFile) in `~./ssh/config`, you can use the host name directly
```bash
docker context create <remote> --docker "host=<remote_host>"
```

Copy required files & folders to remote
```bash
scp -r build/ <remote_host>:~/build/
scp -r etc/  <remote_host>:/etc
```

### Build and run Docker container in remote context
```bash
docker-compose --context <remote> up -d --build
```
