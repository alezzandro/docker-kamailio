# docker-kamailio
Dockerfile for getting latest stable release of Kamailio sip server deployed on latest fedora docker image!

Current Kamailio release: 4.2.3

Current Fedora release: 21


# Testing
For testing it please download it through DockerHub:
```
sudo docker pull alezzandro/kamailio-latest-stable
```
Run your just downloaded container
```
sudo docker run -d alezzandro/kamailio-latest-stable
```
Now write down Container ID and place it in the next command
```
sudo docker inspect $container_id
```
Now find out IP address of your container from the "docker inspect" command and test it through a simple SIPp scenario

You can use one freely available on the net: https://code.osso.nl/projects/sipp/browser/scenario/keepalive-options.xml

Then execute SIPp scenario
```
sipp 172.17.0.32:5060 -i 172.17.42.1 -p 49001 -m 1 -sf Downloads/keepalive-options.xml
```
