# dhcpd-docker
A DHCP server on docker that utilizes ipvlan network driver to expose the service

## getting started
1. Build the dhcpd image using: `docker build . -t dhcpd:latest`
2. Create a docker network using with ipvlan driver:\
`docker network create -d ipvlan --subnet <your_subnet> --gateway <your_gateway> -o parent=<your_parent_interface> ipvlan0`
3. set your static `ipv4_address` on docker-compose.yaml  
4. run: `docker compose up -d`\
Your dhcp continaer should be visible by the ip address you set on docker-compose file
