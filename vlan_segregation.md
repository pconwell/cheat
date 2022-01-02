# Unifi USG <-> Proxmox <-> Pihole

VLAN segregation setup using Unifi/USG, with pihole (and a lot of services running on Proxmox).

## Build VLANs
> by default, Unifi routes all traffic across whatever networks are set up on the router. For example, if you have a 192.168.1.0/24 network for your user devices and a 192.168.10.0/24 network for your IOT devices, Unifi will route all traffic between these two networks.

We will start by setting up the VLANs first. Just know that there won't really be much difference at the moment other than your VLAN devices will have different IP addresses. In other words, we will sort our devices into IP address groups, but otherwise there won't be any real changes to your network (though some IOT devices will be unhappy - more on that later).

For our purposes, we will divide the network into seven groups:

1. Infrastructure (router, switches, APs, proxmox host, etc)
2. Services (graylog, pihole, plex, wireguard, etc)
3. Users (phones, laptops, etc)
4. Playland (xbox, roku, etc)
5. Cameras (security cameras)
6. idIOTs (Internet of Thing / IOT devices)
7. Guests (technically, we won't be setting this up here - so you can ignore it for now)

We will create a new "corporate network" (don't ask - I don't know why Unifi uses that terminology) for each VLAN. Go into `Settings` -> `Networks` -> `Create New Network`

There isn't too much that needs to be configured for each network. Give it a name and VLAN tag as desired. For example, `services` might be vlan `10`. Assign a gateway IP as well. For simplicity, it helps to include the VLAN tag in the gateway IP. For example, you could use 192.168.**10**.0/24. Note the /24 at the end. This is CIDR notation - which we will not discuss here. Just know that the /24 sets the size of the network. `/24` is 256 address. `/28`, for example, would be 16 addresses.

Then set the DHCP range (the range of IP addresses that will be assigned to devices as they connect to the network - assuming you don't manually set static IP addresses).

Lastly - you will need to set the DHCP Name Server IP address. This can be left to auto, but if you are using pihole, you will want it to be the IP address of the IP service.

(You can also set the DHCP Network application IP address as the IP address of the Unifi Controller Software host, but this is optional).
