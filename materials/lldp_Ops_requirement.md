LLDP Requirements
LLDP (Link Layer Discovery Protocol) is a protocol used to discover and manage network devices and their connections in a Layer 2 network. When implementing LLDP on a microwave network element, the following operational requirements should be considered:

The LLDP shall be implemented on the control construct of the device.
1. Enable/Disable LLDP (Configuration)
Enable/Disable LLDP should be supported on the individual interface level and also on the Global level.
Enable/Disable shall be activate/deactivate for both Tx&Rx
Enabling/Disabling LLDP on device level should enable/disable on all interfaces.
Enabling/Disabling LLDP on interface level should enable/disable only on the specified interface
2. LLDP attribute (Configuration)
The below configuration is Global and will be applicable to all interfaces.
msgTxInterval - Configuration to set the interval between the transmit cycles (1-3600)
msgTxHold - Hold constant (1-100)
TTL = msgTxInterval * msgTxHold
If msgTxInterval is configured to 10 and msgTxHold configured to 5, then every 50 seconds the neighbouring information is updated.
3. LLDP Status (Running DB)
LLDP status shall retrieve whether LLDP is enabled or disabled on all the available interfaces.
4. Retrieve LLDP neighbours
While retrieving the LLDP neighbours, operations requires the following the neighbour information.

Below is an example with two interfaces.

Interface 1 name: The unique interface name describing the position of the interface for ex: 0.2.1

Remote System name: The mount point name what is available on the external Label.
Remote MAC: The MAC address of the Main Unit
Remote Management IP (ipv4): The management IP associated to the NE.
Remote Interface name: The unique interface name describing the position of the interface for ex: 0.2.1
Interface 2 name: The unique interface name describing the position of the interface for ex: 0.1.1

Remote System name: The mount point name what is available on the external Label.
Remote MAC: The MAC address of the Main Unit
Remote Management IP (ipv4): The management IP associated to the NE.
Remote Interface name: The unique interface name describing the position of the interface for ex: 0.1.2
If the neighbour is down or the remote interface is not provisioned, all the above values shall be blank.
