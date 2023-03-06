# What Is Eanix?
[Eanix](https://eanix.net) is about home servers for you, you and friends, or your entire family. The idea is to create a layer of software on top of existing applications further abstracting the difficulty of setting up a home server. Some similar services would be OMV, ASUSTOR, and Umbrel.

# What is Eanix Self-Hosted?
[Eanix Self-Hosted](https://build.eanix.net/) is the build we use at the core of Eanix. It's what we build our interface on top of. Eanix Self-Hosted has all of the capabilities of the PerfectMediaServer over at [PerfectMediaServer.com](https://perfectmediaserver.com/), but with a slightly different approach.

Eanix Self-Hosted, or ESH, is a 100% open-source technology stack that enables you to explore a new type of application across your devices. These applications do not store data on the device, but on the server that the applications reside on. They are based on the same technologies as the web, and is a subset of Web 3. The idea is to run your own cloud at home and get away from "big data," which gives you full control over your data and privacy.

The ESH hardware we run on is actually gaming hardware. Gaming hardware is designed to be put to the test on a regular basis and has a greater lifetime, even when running 24/7. Most gaming hardware also has a lot of SATA ports built into the motherboard, as opposed to the 2 that a PC from a top brand may come with. This gives us the ability to add the necessary hardware to reach our target requirements. 
## The Requirements
Our requirements can be defined as follows:
- Operate as the home router, replacing high end $500 home routers.
- Operate as a Network Attached Storage (NAS), including bitrot protection
- Be resillient to power failures
- Be secure against both internet and local network based attacks
- Be able to handle high throughput sequential read and optionally high throughput sequential write
- Be able to handle databases and large sets of files with SSD speeds
- Support video transcoding of multiple video streams
- Support machine learning, CUDA based, applications such as real-time voice recognition and parsing
- Support an App-Based architecture using Docker containers, with docker-compose files as the app installer.
- Support protecting any application with OAuth2 (Single Sign On)
- Support being publicy accessable over the internet from anyone and any device
- Support Email at home (via inbound and outbound relay)
- Support having bootable desktops baked in
- Support PXE boot of operating system and recovery images
- Support backups to S3 buckets or SFTP

## Hardware

This setup is extremely complex compared to your normal builds and includes various components all baked into one PC. Not all features are required and each one has it's own independent hardware requirements. Be sure to read our [Minimum Hardware Requirements](https://build.eanix.net/minimum-requirements/) and [Hardware Recommendations](https://build.eanix.net/hardware-recommendations/) before embarking on this journey. If you are building from scratch, try our guide on [Building Your PC](https://build.eanix.net/building-your-pc/).

Unlike PerfectMediaServer, ESH does not support building out your hardware over time drive-by-drive. Drives must be purchased in at least multiples of 2, or be available prior to the setup. If you have been using PMS or anything similar, ESH is something you can switch to after you have all of your hardware.

# Where Do I Start?
If you are new to the space, I would recommend trying out [PerfectMediaServer](https://perfectmediaserver.com) while you build out your hardware inventory. Eanix Self-Hosted is intended to be for hardware builds designed from the start for the task, or for yearly periodic upgrades, such as using your tax return every year. We offer PC [reference builds](https://build.eanix.net/reference-builds/) with parts lists for Newegg.com to get you started, as well as [what to look for when buying used hardware](https://build.eanix.net/buying-used-hardware/) for when searching eBay or Facebook Marketplace. 

# What Started This?
I first started playing with Docker in 2016 and after I began investigating ways to host Wordpress. I wanted to be able to set up Wordpress in Docker containers to build out a hosting platform that offered 30 second "logo->website" generation, with every instance managed and built to scale automatically. I began researching Kubernetes and Docker, but life happened and I had to drop the project, which wasn't built out enough to be feasable on a small startup budget. I needed profitable from the start.

Fast forwad 4 years, I had used VMWare Workstation for years prior to 2020 to run an Ubuntu VM on my Windows gaming PC. I read about Docker Desktop and wanted to try it, but went through hell and back trying to get VMWare and Hyper-V to work on the same PC. I eventually moved to using Docker in Ubuntu and to store my files on disks that were passed through from Windows, but there were two issues that always bothered me:
- Passing through hard drives in VMWare Workstation means they are raw partitions and could accidentially be erased by Windows at any point.
- Restarting my Windows PC also restarted my Ubuntu PC, and I was probably doing something in my Ubuntu PC when an app I installed on Windows needed a reboot. Not to mention it took all of my services down.

So I began looking for a way to reverse the roles and use a different type hypervisor. I read up on it for some time and it seemed that everything had it's own shortcomings. I decided to give ESXi a try and was successfully able to get ESXi 6.7 installed on my gaming PC using a community Realtek driver. 

Unfortunately, VMWare dropped support for the Linux side of ESXi in version 7.0, so the Realtek driver no longer works. Not only that, but I started encountering various issues like blue screens while encrypting with Bitlocker, or issues passing through my video card to work as the primary driver of my monitors. Eventually, while looking into GPU Passthrough, I came across Proxmox. I was quick to give it a try, because I really wanted this set up to work. I wasn't sure if it would ever work or if doing so was even possible. Much to my surprise, Proxmox worked! GPU Passthrough works great, as did drive passthrough. Instruction sets from the CPU can even be used by the VMs which I needed because I'm using AES for drive encryption and I/O wait was a real problem in VMWare Workstation and even on VMWare's ESXi. 

There are still a few shortcomings though that I wanted to address, which are listed above under the requirements section. I also want to bring this technology more mainstread and increase adoption as families can greatly benefit from using self-hosted software over the public cloud, like your children not being subjected to bullying or weight loss ads, or a child not getting access to the entire Netflix catalog that you might not approve of. There are still a few hurdles though, like it being illegal to backup your DVD's and Bluray's to a hard disk that you own, despite not sharing them. It doesn't matter if you keep the UPC code as a proof of purchase or not. These are hurdles that I want to help address, but it requires a foundation to stand on, otherwise you'll just sink in the sand as soon as it rains.
