# transitime-docker

Things to make transitime go:

- Ubuntu
- sudo apt-get install git
- git clone https://github.com/TheTransitClock/transitclockDocker.git
- curl -sSL https://get.docker.com/ | sh  (i.e. install docker)
- Configure agency details in the go.sh script. Here you set the agency name, agency id** (as in GTFS feed), GTFS feed location and GTFS-realtime vehicle location url.
- ./go.sh

**AgencyId is optional in GTFS so just set to 1 if none specified.

The go script will build the transitime container (takes a long time), start the postgres db, create the tables,
push the gtfs data into the db, create an API key and then start the api service and web user interface service. 

To view web interface
```
http://[ipaddress]:8080/web
```
To view api
```
http://[ipaddress]:8080/api
```

You can get the ip address by running
```
docker-machine ip [machine name]

docker-machine ip default
```



