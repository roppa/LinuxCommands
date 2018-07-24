# SCP/SSH

### SCP to Server
SCP all files in `/path/to/files/` to `10.10.10.10` to `serverDIR`

`scp -r /path/to/files/* 10.10.10.10:./[serverDIR]`

### SCP From Server
SCP all files from `serverDIR` on `10.10.10.10` to the current local directory

`scp 10.10.10.10:./[serverDIR]/* .`

### SSH Tunnels
Create SSH tunnel that uses port `9925` (localhost) and will route that traffic to `10.10.10.10`, which will then forward the request to `20.20.20.20:25`.

`ssh -L 9925:20.20.20.20:25 10.10.10.10`

Create SSH tunnel that when a connection is made to the port `5044` on `10.10.10.10` it should be forwarded to port `5044` on your local machine.

`ssh -R 5044:localhost:5044 10.10.10.10`

# Symbolic Links

### Symbolic Links
Create a symbolic link called `myApplication` that is linked to `myApplication_1.0.3`

`ln -s myApplication_1.0.3 myApplication`

# Exploratory Commands

### Find processes running on specific port

`sudo lsof -i tcp:port`

# Running Commands

### Run command every interval

##### Every 1 second

`while sleep 1; do [cmd]; done` 

`while sleep 1; do echo "Hello"; done`

##### Every millisecond

`while sleep 0.1; do [cmd]; done` 

`while sleep 0.1; do echo "Hello"; done`
