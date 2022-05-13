# Gnome for Slackware 15.0
## Overview
The goal of this project is to provide the GNOME desktop in "SlackBuild" format for usage on Slackware 15.0. The idea is to use any existing packages from slackware or slackbuilds.org, and add what is required to complete the GNOME desktop.

The slackbuilds in this project must be able to build on slackware 15.0, with no custom upgrades to base Slackware packages. When Slackware 15.0 released, GNOME 41 was the latest version. The builds here will generally be from that same release, although it may vary depending on pre-existing package versions in Slackware and slackbuilds.org.

## The Core Components
Modern desktop environments like GNOME and KDE have many components, making a comprehensive build difficult to manage. This project takes the approach of building the "core components" required for GNOME, and then the user can add on components from there to build the desired system.

At the core on GNOME is the "gnome-shell" graphical environment, along with the "gnome-session" session manager, and the "gdm" display manager, used for login and screen locking functionality. With these three packages installed, gnome will be functional and applications from Slackware can be used for everything else.

Note that gnome-shell has a naumber of dependencies in the form of programs and libraries, used to give it functionality. Key dependencies that are used to build gnome-shell include evolution-data-server, gnome-online-accouts, gnome-control-center, gnome-settings-daemon, and the mutter window manager/wayland compositor. 

## Additional Components
The core components only provide the basic GNOME desktop, along with some things like a panel, application menu, and control center to name a few. Several additional packages are provided to allow for easier customization of the GNOME desktop, mainly focused on enabling extensions from extensions.gnome.org, and adding a few other basic programs.
 - nautilus (GNOME's file manager)
 - gnome-terminal (there are existing terminals on Slackware, but this one matches the look of gnome)
 - gnome-backgrounds (some gnome provided wallpapers)
 - gnome-extensions (a control panel for managing extensions)
 - gnome-tweaks (useful for changing themes, adding back the minimize button, changing wallpapers)
 - chrome-gnome-shell (browser integration for extensions.gnome.org)

 Note that "chrome-gnome-shell" is the "system side" of the browser integration for gnome extensions. You will also have to install the browser extension itself to enable switching extensions directly from extensions.gnome.org. If you omit browser integration, you can still manually download and install extensions. The extensions system is useful for configuring the GNOME desktop. Some useful extensions include:
 - libappindicator (provides a system tray for things like hplip, bluetooth, discord, etc.)
 - Hide/Remove the activities button
 - Add an applications menu (this one is built-in)

 ## Building and Installing
 This is a work in progress, but the general idea is that these will all be on slackbuilds.org one day. Once that is the case, you can use 'sbopkg' to build the core components, and additional components. There is also a "queue file" for sbopkg that you can use to automatically build the core and additional components, in the correct order. See the "gnome-build-order.sqf" file provided in this repo.

 NOTE ABOUT USERS/GROUPS (colord, avahi)

 NOTE ABOUT BUILD ENVIRONMENT VARIABLES (INTROSPECTION, VAPI, VALA, WEBKITGTK)
 