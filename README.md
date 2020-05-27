# LoRaWAN Network Setup
Notes about setting up a LoRaWAN network, from gateway configuration to application server.

## LoRaWAN Network Main Components

A LoRaWAN network is mainly composed by end-devices, gateways, network servers and application servers. Using a star-of-stars topology, gateways relay messages between end-devices and a network server, which sends the messages to the associated application server. In the next sessions each of the components will be described.

### End-Devices

Also known as motes, end-devices may be sensors, trackers, and other devices that send data in the network. In a LoRaWAN network, an end-device doesn't communicate with other end-device directly, they have to send the message to the network server. There are three classes of end-devices:

#### Bi-directional end-devices (Class A)

This class of devices stay in sleep mode most of the time. They wake up to trasmit data, open two receive windows and go back to sleep. Power saving is the main goal of these devices, which are mostly battery powered or harvest energy from it's environment.

#### Bi-directional end-devices with scheduled receive slots (Class B)

This class of devices works like Class A, but with scheduled extra receive windows.

#### Bi-directional end-devices with maximal receive slots (Class C)

This class of devices operate with nearly continuous receive windows, which allows the applicaton to send data to the device at almost any time. This characteristic makes this class more power hungry, one time the radio is always (or almost) turned on.

### Gateways

Gateways, also called concentrators or base stations, have the function of relay messages from end-devices to a network server via secured standard IP connections.

One gateway can handle thousands of nodes and relay them to a network server, covering a radius varying from 2 km to 15 km, depending on environmental conditions.

### Network Servers

Network Servers are reponsible for receiving data from one or more gateways and de-duplicating packets received by two or more gateways.
After packet reception, it is sent to the application server.

### Application Servers

Application Servers receive data from Network Servers and take actions based on them.

