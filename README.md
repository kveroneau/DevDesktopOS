# DevDesktopOS

A Custom spin of the Debian Live CD tailored specifically for development with as minimal configuration needed to get up and running.

The idea behind this project eventually is to provide people who want to get up and running with a development system as quickly as possible and with as little configuration as possible.  The idea is to have sane defaults that can tailor to most developers, and since it is based on the Debian Live project, it has support for persistence, allowing developers to alter the configuration in the environment which can then be used across reboots.

[Debian Live Manual](https://live-team.pages.debian.net/live-manual/html/live-manual/index.en.html)

This is also a git project, so if you feel that you'd prefer **GNOME** over **Plasma**, or want a more minimal Window Manager like **Awesome**.  You can fork the repo and make the needed package updates within the `config/package-lists` directory.  Since this is just building a live environment, which on a decently powerful machine, does not take very long, there is less risks to experiment with different package configurations in a fork.

At the moment, it is very barebones, the main highlight features of this very early alpha release(*if you can even call it that*) is the following:

  * Fully configured and ready to use **libvirt** and **Virtual Machine Machine**.
    - Virtual Machine Machine is a GUI VM manager which can manage the following virtualization tech:
      - QEMU/KVM
      - LXC
      - Xen
      - Hyper-V
      - And I think a few more.
    - In a future version there will be full support from boot to use `vagrant` to spin up `libvirt` compatible images with it for development and testing purposes.
    - The Live User is part of the `libvirt` group which will give you access to Virt-Manager.
  * Fully configured and working Docker for Linux.
    - The Live user will be a part of the `docker` group, allowing normal docker commands to be performed from IDEs and such.
  * OBS Studio and KDEnLive
    - Allows for the easy recording and streaming of coding sessions if needed.  This can be easily removed by removing the packages from the packages-list before building.
  * Very basic set of dev tools for now, still deciding on how much I want to include.  I am guessing many will expect the Chrome browser, but I don't think I can directly include it, but I can explain how to build it into your own live image on your own, it's really easy to add.

## What are the other benefits of this over a regular system?

Well, it is much more difficult to break a system which boots from a Live media, or rather a read-only file system.  This image could for example be used as a base for a company-wide developer image, which can contain all the needed tools the developer would need, and the Linux administrators can then handle the updates via the update and distribution of a new live image.  It can also be booted up within a virtual machine on a Windows desktop to have a full Linux desktop for development ready to go.  It also makes it easier to both onboard and get a developer whom might have a down system back up and developing, saving the company money.

## Ideas for the future:

I'd personally love to grow this into a specialized Debian-based Linux distro made by developers for developers.  If there is enough interest in such a Live System, and if there is a place where I can freely host ISOs, I can do all the image building.  As it stands, without a audience, building and hosting an ISO isn't worth as much effort as it would be to add new features to this live image for when people do stumble across it.

Here is an outline of other possible ideas:

  * Various DevDesktopOS *spins*
    - Such as one which is for web development, containing *node.js*, *npm*, etc...
    - One for multimedia development, with tools like Blender and such preloaded and configured.
    - Different technical professions, such as DevOps with related deployment tools.

The main idea is for the environment to be fully functional for almost any user right from boot.  Much like the spirit of old Slackware and other specialized Live distros like *Dyne:Bolic*, which were both a celebration and a showcase of many open source projects in a super easy to consume format, a LiveCD.  I always found it really cool to boot up a specialized LiveCD like *Dyne:Bolic* and was able to explore a world of fun open source multimedia software I've never seen and sometimes never heard of before.  I miss those days when Linux LiveCDs had an amazing purpose, to not just introduce people to Linux, but to introduce people to technology in a really easy, risk free way.  There was no drivers to install, no software to install, no complex configurations to manage, no needing to hop on multiple forums to find a specific configuration, in most cases a lot of these LiveCDs did work for the majority of people with no additional effort.  This is the spirit I want to try and bring back with *DevDesktopOS*, a Live CD to allow that fun sense of exploration again, perhaps finding or using some open source software you may never have otherwise tried.

## Current project plans

Essentially since I am currently only building this for myself at the moment, and it isn't really difficult to change if it gains attention.  I will be focusing on trying to replicate my current `buster` Linux workstation as a full LiveCD, which will include most of the software packages I have installed on my normal development system, some pre-configured with some of my presets of course.  This project can otherwise be a good starting point for anyone wanting to build a Debian Live image of their own.  As the official documentation can be a bit much to go through.
