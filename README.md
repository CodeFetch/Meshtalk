# Meshtalk
Meshtalk is a P2P messaging software intended to be used on mesh networks.
It runs on routers with OpenWrt that are e.g. part of a wireless mesh network. 

The user interface is a webpage served by one of the routers the client (user) is connected to. This user interface utilises the webbrowser's WebRTC-API to establish secure, encrypted connections between the users. 
No third party software has to be installed on the client's machine if its browser supports the WebRTC-API (e.g. Google Chrome).

The addresses of the users' contacts are either found out by the router sending broadcast-messages to the other routers asking for the specific contact's (encrypted) address or if that failed by asking one of the contact's "home" routers for the address. The user that shall be contacted repeatedly tries to send its address to its "home" routers when it changes.
Thus a user can even be contacted if broadcast traffic is being filtered on a higher level of the mesh network (e.g. on Supernodes in many Freifunk communities).

Please note: The addresses are always OTP-encrypted with random keys that were exchanged in the last session the users were connected to each other. The encrypted address will be saved by the routers for every combination of the users' devices.
Prioritised ways to contact a user allow the use of multiple devices and bouncers.

Optionally a distributed hash table can be used instead of the "home" routers to make users harder to track. If many people use this service this feature does only scale if many routers have a decent amount of memory (more than 32MB RAM).
