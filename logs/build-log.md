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

## Day 1 09/02/2026
### <ins>**Goal:**</ins> Fully deploy basic infrastructure

* Proxmox on flex4
* Linux on chromebook
* Tailscale on Surface pro, proxmox server, and chromebook
* Confirm they can all talk to each other

### <ins>**What Happened:**</ins>



plugged in my laptop docking station bc surface pro does not have a built in usb port - searched yt for a good tutorial and landed on 2 vids by sjstech and digital mirror (make sure to link in syn) - tried to install proxmox, realized it would wipe by usb, bought new at store

download was successful, opened a claude cowork session to help explain the process while i followed tutorial - opened bios on flex4 and selected to boot frm usb

![alt text](Flex4_BIOS.jpg)

Worked! - selected graphical install and continued with process. kept harddisk options all stock: ext4 filesys and 237 hdsize. 

### <ins>**What broke:**</ins>

First USB I tried didint work. tries to run rufus but it gave me this error. I think its bc i renamed the usb or that the port i was using because i tried another one in a different port and it worked perfectly

![Rufus USB Error](Rufus_Error.png)

After starting up proxmox I ran into: 

![alt text](Proxmox_Virt_Error.jpg)

I asked claude what could be the issue, and after aborting and going back to BIOS i noticed that virtualization wasnt enabled. after I did that everything started working as intended

![alt text](Virtualization_Disabled.jpg)

### <ins>**What I learned:**</ins>