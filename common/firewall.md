# Firewall

## Installation and config
As we are required to close evey other port but 4242, we need to configure a firewall with those rules in order to make it happen. The firewall we are using is UFW (Uncomplicated Firewall). This will allow us to configure the iptables (firewall rules for linux) we are required to do.

UFW is not installed by default on our system, so we will have to install it. To do so, we can use ``sudo apt install ufw`` with our user account (not root).
Once it's installed, configuring it is super easy (hence, it's name). We just have to execute ``sudo ufw allow <port>/<protocol>``, substituing ``<port>`` and ``<protocol>`` by ``4242`` and ``tcp``, since ``ssh`` service runs on ``tcp`` protocol.
Now, if we enable the ``ufw`` service with ``sudo ufw enable``, we will only be able to acces port ``4242`` from the outside.

## TCP? vs UDP

On the internet there are two main protocols (actually 3): **UDP** and **TCP**, and the y have multiple use cases and peculiarities. Both of them are part of the Transmission layer on the OSI model.

### TCP

**TCP** stands for _Transmisson Control Protocol_ and it stablishes connections among computers on a network to transmit information. It makes sure that the packets transmitted arrive to their destiny and sends them in a particular order: When the packet arrives, the next one is transmitted.

### UDP

**UDP** stands for _User Datagram Protocol_. This protocol is meant to send Datagrams, a way of encapsulating data in a way that can be sent faster without requiring a previous connexion to the destiny user. It does not check if the packets arrived or not neither ensures that data arrives in a particular order: Packets can overtake other packets.

This deffinitions allow us to make a quick distinguishment: Speed and Reliability. If we want our packets to arrive quick and we don't care about if all of them arrive to the receiver or if the order get's altered, like in a VoIP call, we will use **UDP**. If on the other hand we want our packet to arrive in a particular order (or just make sure they arrive) such in a secure communication between computers, like SSH, we would use **TCP**



