**SMB-Hackathon Problem Statement**
## How do we automate the Smart Machine Bidding procedure for the LPWAN devices in order to reduce the costs of an IoT network?

MXC foundation focus on connecting Low Power Wide Area Network (LPWAN) technology with the blockchain as an infrastructure for Internet of Things (IoT). MXC automates machine-to-machine (M2M) transactions and provides a device data economy. The pricing policies of data transmissions through gateways in LPWAN are determined by MXC Smart Machine Bidding (SMB). In the SMB, based on the bidding strategies provided by the device owners, and the gateway owners, the payments for using downlink / uplink LPWAN resources will be determined.The following parameters are set by the device in bidding strategies of the SMB:


• **max\_bid:** the maximum bidding price defined by the device owner shows
the upper payment threshold of the device (in MXC tokens) for the down-
link request.

• **max\_delay:** this parameter defines, under certain circumstances, the max-
imum acceptable\_delay (in seconds) for the packet to be sent. If max_delay
is reached, the packet will not be sent and the cloud will notify the client
about the rejection of the downlink request.

• **accepted\_delay:** the tolerable delay defined by the client (or device owner)
to indicate the time period a packet is willing to wait for the lowest possible
price. Lowest possible bidding price is the current lowest bid of the available
gateways for the device. 


Each gateway provides a value on using its resources called min\_bid. The device in order to use the gateway downlink resource, should bid at least min\_bid value. If multiple devices in a same time wants to use a downlink resource of a gateway, the one which define more max_bid will be the winner.

More details about bidding procedure are provided in MXC Smart Machine Bidding white paper (available in the repository stated below and the MXC website).

Based on downlink / uplink data flow of the device owners and their requests, MXC cloud can provide data driven automated smart machine bidding.  max_delay parameter is mainly related to the application and the priority of the data which is known by the device owner/client and is defined by the requirement of the provided application by the device. 
At the other hand, accepted\_delay, and max\_bid parameters should be provided by the device owner (or the client) in some way to make a balance between priority of the related uplink/downlink data and the corresponding data transmission cost. These two parameters (accepted\_delay, and max_bid) can be automatically provided for the device owner to make this balance.

Your task is to develop an automated solution (e.g. based on Machine learning methods, dynamic algorithms or greedy algorithm) which provides near-optimum value for accepted\_delay and max_bid parameters to reduce the total cost of the LPWAN for the user. 

In the input file, you will receive max_delay, payment limit which the data owner wants to pay in total (for all of the transactions), and the downlink resource usage history of the device and other devices. Your program (preferably in Go) will be evaluated by output efficiency (based on the test cases of LPWAN data simulation), and solution explanation (provided in your documentation). Note that you can provide multiple solutions and do the implementation as much as you want/can. A sample input file and its details will be provided in this repository.
