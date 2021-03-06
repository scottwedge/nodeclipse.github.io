---
layout: share
title: Starting with Java and Node.js development on Ubuntu Linux
date: 2015-7-9
categories: [ubuntu,linux,java,nodejs,2015]
---


### {{ page.title }}

<p class="meta">{{ page.date }}</p> by Paul Verest

[Ubuntu](http://www.ubuntu.com/) is major Linux distribution 
([wikipedia article](https://en.wikipedia.org/wiki/Ubuntu_(operating_system))

One should select LTS version, as for example [Help](https://help.ubuntu.com/)
is full only for LTS versions and Node.js packages are [supported for LTS](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager)
but not latest versions.

#### Installing Java JDK 8

There are many [Java implementations for Ubuntu](https://help.ubuntu.com/community/Java).
Let's stick with Oracle JDK:

<http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html>

	sudo add-apt-repository ppa:webupd8team/java
	sudo apt-get update
	sudo apt-get install oracle-java8-installer
	
Check what exact version you got:

	java -version
	javac -version	

See also <https://www.digitalocean.com/community/tutorials/how-to-install-java-on-ubuntu-with-apt-get>

#### Install Enide 2015 (Eclipse-based IDE)

Based on <http://ubuntuhandbook.org/index.php/2014/06/install-latest-eclipse-ubuntu-14-04/>

1. Download Enide for Linux, e.g. [Enide-2015-7](http://sourceforge.net/projects/nodeclipse/files/Enide-2015/7/Enide-2015-7-linux-gtk-x64-20150706.zip/download).
2. Extract to e.g. `/opt/Eclipses/Enide-2015-7-linux-gtk-x64-20150706/`

	`sudo nautilus ~/Downloads`
	`sudo nautilus /opt`

3. Allow `eclipse` to be executable. From the `/opt/Eclipses/Enide-2015-7-linux-gtk-x64-20150706/eclipse/` folder

	`sudo chmod -R 7555 eclipse`
	
4. Create shortcut

	`sudo gedit /usr/share/applications/enide-2015-7.desktop`
	
paste

	[Desktop Entry]
	Name=Enide-2015-7
	Type=Application
	Exec=/opt/Eclipses/Enide-2015-7-linux-gtk-x64-20150706/eclipse/eclipse
	Terminal=false
	Icon=/opt/Eclipses/Enide-2015-7-linux-gtk-x64-20150706/eclipse/icon.xpm
	Comment=Enide 2015-7 (Eclipse 4.5 Mars-based)
	NoDisplay=false
	Categories=Development;IDE;
	Name[en]=Enide-2015-7

See also <http://askubuntu.com/questions/337281/installing-eclipse-kepler>

#### Installing Node.js

<https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager>

<https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server>

	sudo apt-get update
	sudo apt-get install nodejs
	sudo apt-get install npm
	
Or the latest using <https://github.com/nodesource/distributions>
	
	curl -sL https://deb.nodesource.com/setup_0.12 | sudo -E bash -
	sudo apt-get install -y nodejs	
	
	