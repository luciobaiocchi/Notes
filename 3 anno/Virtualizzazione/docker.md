# Immagini

tre tipologie di imagini: 
- base 
- slim (più leggera)
- alpine (ancora più òeggera ma basata su linux alpine)


## custom images 
# Debugging 
exec to exec a process on an already running container, -it interactive and tty (fon comandi history and autocomplete).
```bash
docker exec -it <container_id> /bin/bash
```

# Persistence

Any time we run a container all the contents are deleted.

```bash
docker run -v mydata:/data <container_id>
```

## Mount types

| Volumes  | Bind-mounts | Tempfs mounts |
|----------|-------------|---------------|
| persitent| persitent   | Non persistent|
| newer    | Older ||
| more features | less features||
| managed by docker daemon | mpunted on host file ||

**Syntax**

volumes -> `-v mydata:/path/in/container`
bind-mounts -> `-v ./mydata:/path/in/container`

**which one**

- volumes:
  - often better in production
  - not dependent on host filesystem
  - easy to share across container
- bind mounts:
  - more convenient in **developement**
  - quick share with host
  - readonly mount: 
  - `-v ./mydata:/path/in/container:ro`
  
# Layers

like image diffs, each command creates a layes. Docker try to use cached layer. Changing a command will rebuilt all the succesives layers that depends on the changed ones although they wasn't changed.

# Networking

Container networking refers to the ability for containers to connect to and communicate with each other, or to non-Docker workloads.

The following example creates a network using the bridge network driver and running a container in the created network:

```bash
 docker network create -d bridge my-net
 docker run --network=my-net -itd --name=container3 busybox
```
## Drivers 
`bridge`    The default network driver.
`host`	Remove network isolation between the container and the Docker host.
`none`	Completely isolate a container from the host and other containers.
`overlay`	Overlay networks connect multiple Docker daemons together.
`ipvlan`	IPvlan networks provide full control over both IPv4 and IPv6 addressing.
`macvlan`	Assign a MAC address to a container.