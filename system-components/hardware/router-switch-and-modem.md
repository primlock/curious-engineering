# Routers, Switches and Modems

What is a router, switch and a modem and how do they work?

<img alt="routers-and-switches" src="figures/router-switch-modem.png"  width=30%>

## What is a Router?

A router is a device that **connects two or more packet-switched networks or subnetworks**. It performs two primary functions:

<img alt="router" src="figures/router.png">

* Managing traffic between these networks by forwarding data packets to their intended IP-Addresses.
* Allowing multiple devices to use the same internet connection.

In order to route the packets effectively, a router uses an internal routing table - a list of paths to various network destinations. A router reads a packets header to determine where it's going, then consults the routing table to figure out the most efficient path to that destination. It then forwards the packet to the next network in the path.

### The Home ISP Router

There is an important destinction between the technical definition of a networking router and a *home router*. Above is the definition of what a router technically does, connecting two or more networks and allowing internet access, but this differs from the what a *home router* is. A home router, often installed by your ISP is a **combo device** serving multiple common networking needs inside your homes LAN:

* Routing: Connecting the ISP's network to your home LAN for internet access.
* Switching: Providing physical ethernet ports for wired home devices like PC's or TV's to connect.
* Wireless Access Point: Providing wireless internet access via WiFi to devices that can send and recieve wirelessly.

Routing is just one of the jobs your home router is doing and if you broke it down phsically like in enterprise, you would see these devices set up independently.

<img alt="home-router" src="figures/home-router.png"  width=30%>

### What Layer Does it Operate On?

A router operates at **layer 3 - the network layer** of the OSI model. It inspects the IP addresses of the incoming data packets and perform the routing function to the destination network with it's internal routing table.

## What is a Switch?

A network switch **connects devices within a network**, often a local area network, and forwards data packets to and from those devices. A switch only sends data to the devices that is intended for, which may include another switch, a router or a users computer (but not to a network of multiple devices).

<img alt="switch" src="figures/switch.png">

### What Layer Does it Operate On?

Switches can operate at **layer 2 - the data link layer** or at **layer 3 - the network layer** of the OSI model. Layer 2 switches forward data based on the destination MAC address while the layer 3 switches forward data based on the destination IP address. Some switches can do both. Most switches are layer 2 and connect devices in their network over ethernet cables.

## What is a Modem?

A modem is a device that allows devices to connect to the internet by converting digital signals into analog signals that can be transmitted over telephone lines or cable networks. They also perform the opposite action of converting analog signals that come over transmission medium into digital signals. The word *modem* stands for **modulator-demodulator** to express it's function.

<img alt="modem" src="figures/modem.png">

### What Layer Does it Operate On?

Modems operates at **layer 1 - the physical layer** of the OSI model converting digital signals into analog to be transmitted and received over the network. They can also operate at **layer 2** to handle error-free data transmission and data framing. This ensures data is packaged corretly and transmitted reliably across the network.