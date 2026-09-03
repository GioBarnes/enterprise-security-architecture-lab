# Home Lab Build log

The purpose of this document is for be to be able to log my raw progress as I complete this lab. These will be in chronological order, as I write down what I did each day. For a synthesized writeup version of these notes, see the other folders in this repository. 

    Log Format: 

    Day X mm/dd/2026
    ---------------------
    Goal: 
    What Happened: 
    - xyz
    - xyz
    What broke:
    - xyz
    - xyz
    What I learned:
    - xyz
    - xyz

## Day 1 and 2 09/02 and 09/03/2026
### <ins>**Goal:**</ins> Fully deploy basic infrastructure

* Proxmox on flex4
* Linux on chromebook
* Tailscale on Surface pro, proxmox server, and chromebook
* Confirm they can all talk to each other

### <ins>**What Happened:**</ins>



plugged in my laptop docking station bc surface pro does not have a built in usb port - searched yt for a good tutorial and landed on 2 vids by sjstech and digital mirror (make sure to link in syn) - tried to install proxmox, realized it would wipe by usb, bought new at store

download was successful, opened a claude cowork session to help explain the process while i followed tutorial - opened bios on flex4 and selected to boot frm usb

![alt text](/screenshots/Flex4_BIOS.jpg)

Worked! - selected graphical install and continued with process. kept harddisk options all stock: ext4 filesys and 237 hdsize. 

Continued w/ setup, matched host ip to router, assigned ip to flex4 (192.168.12.250) and set pw. Had to buy ethernet cable to connect it to my router - was able to get proxmox fully up and running!

![Proxmox setup](</screenshots/Proxmox_Complete.png>)

per instructions in sjsltech vid, changed some config files to prevent the flex4 from always having to be open to keep running (allows me to close laptop and have the screen turn off without the server stopping) - helps prevent burning onto screen and power usage

config file changes:
![alt text](</screenshots/Configchange1.png>)
![alt text](</screenshots/Configchange2.png>)
![alt text](</screenshots/ListofCmds.png>)

Watched miles matias yt vid on installing tailscale and set it up on both the surface pro and my proxmox server to allow remote communication frm anywhere

![alt text](</screenshots/Tailscale.png>)

then used the tailscale website for proxmox's guide to get a domain to sign the certificate so I dont have to see the "unsafe" screen everytime - then i checked and verified that my surface pro and flex4 could communicate via ping 

![alt text](</screenshots/Certificate.png>)

### <ins>**What broke:**</ins>

First USB I tried didint work. tries to run rufus but it gave me this error. I think its bc i renamed the usb or that the port i was using because i tried another one in a different port and it worked perfectly

![Rufus USB Error](/screenshots/Rufus_Error.png)

After starting up proxmox I ran into: 

![alt text](/screenshots/Proxmox_Virt_Error.jpg)

I asked claude what could be the issue, and after aborting and going back to BIOS i noticed that virtualization wasnt enabled. after I did that everything started working as intended

![alt text](/screenshots/Virtualization_Disabled.jpg)

### <ins>**What I learned:**</ins>