<p align="center" width="100%">
<img src="images/eanix-logo-transparent-small.png" />
</p>


# Home Server
If you are looking to build a home server, or personal cloud, or self-hosted stack, look no further. This site is intended to provide you with instructions on how to set up and
configure your own home server using high end gaming hardware. It is powered by free and open source software.

The stack mix that goes into the home server consists of a Linux hypervisor, Linux virtual machines, and Linux Docker containers. You can choose to use the home server as a Desktop
as well and run Windows on it, if you would like. The core virtual machines will all run Debian or Ubuntu, except the firewall which runs either [pfSense](https://build.eanix.net/pfsense/) (free) or [Arista](https://build.eanix.net/arista/)
(paid). Additionally, the home server utilizes the [ZFS](https://build.eanix.net/zfs/) filesystem, [docker-compose](https://build.eanix.net/docker-compose/), [ProxMox](https://build.eanix.net/proxmox/), [Keycloak](https://build.eanix.net/keycloak),
[OAuth2-Proxy](https://build.eanix.net/oauth2-proxy/), [Nginx Proxy Manager](https://build.eanix.net/npm/),
[Netboot.xyz](https://build.eanix.net/netbootxyz/), and a backup solution.

We have a lot to do, so if you are ready to get started you can go ahead and skip to the next page, the [overview page](https://build.eanix.net/overview/). If you want to learn more about home servers or myself, keep reading.

# What Is This Intended To Help Me Do?
The intention of this wiki is to walk you through building a home server from scratch. Some basic knowledge of computer hardware is required to achieve this, but it's easy. You don't have 
to be A+ certified to build the home server. This wiki is intended for the enthusiast that already has good hardware or is willing to go out and buy new (or used) hardware that meets the necessary hardware requirements.
If you own a gaming computer, there is a chance you can repurpose it to work as a home server and still game on it with minor upgrades.

# About The Author
<table border="0">
<tr>
<td width="85%">
This guide on building a home server is written and maintained by me, <a href="https://www.linkedin.com/in/daniel-weisinger-4763a4227/">Jared "Daniel" Weisinger</a>, a Christian, and a programmer of 20 years now. My interests include data analytics and automation, and robotics.
<br /><br />I cover a range of topics over on my website <a href="https://jaredweisinger.com/">jaredweisinger.com</a>, consisting of activism as it relates to technology, civil rights, and humanity. 
</td>
<td width="15%" align="right">

![Picture of Me](images/me.jpg)

</td>
</tr>
</table>

# How To Contribute
This wiki is made with [mkdocs](https://www.mkdocs.org/) and hosted on Github. If you would like to add to this wiki, or if you find an error, you can send a PR using the Github link in the top right. 
