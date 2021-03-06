---

copyright:
  years: 2018
lastupdated: "2018-08-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Load Balancer provisioning troubleshooting
This topic provides information on common issues you may encounter while creating a new instance of IBM Cloud Load Balancer.

## Insufficient IP addresses in your subnet
IBM Cloud Load Balancer requires at least two free IP addresses from its private subnet. In addition, if the load balancer is a public load balancer and the **IBM system pool** option is not used, then at least two free IP addresses are needed from your public subnet as well.

## Issues with firewalls on public and private VLANs
Refer to the topic [IBM Cloud IP Range](https://console.bluemix.net/docs/infrastructure/hardware-firewall-dedicated/ips.html#ibm-cloud-ip-ranges) for information on allowing IP ranges through the firewall.
 
## Viewing load balancer error messages
To view error messages for your load balancer, perform the following procedure:

1. Click on the load balancer from the list page to view its details. 
2. Mouseover the error symbol next to the load balancer's status.

<img src="images/lbaas_error_message.png" alt="drawing" style="width: 500px;"/>

If the load balancer is in an `ERROR` state, it cannot be recovered and must be deleted.