---
title: "Windows Subsystem For Linux (WSL)"
linkTitle: "Windows Subsystem For Linux"
weight: 3
date: 2020-09-22
description: >
  Feel the power of Linux and various distros on Windows without using any emulator or virtual disk!
---
#
## Introduction

<b>Windows Subsytem For Linux(wsl)</b> is a GNU/linux enviornment that you can use in your Windows operating system freeing you creating dual boot or installing different virtualisation software or emulator. It provides a basic command line interface / terminal with your prefferd choice of linux distribution.
It's a great option if you want to learn linux but don't want to remove your Windows for some reasons.
![image-intro](https://github.com/hnccbits/cdn/blob/master/images/learn/linux/wsl/SharedScreenshot12.jpg?raw=true)
## Pre-requisite
x64 - Windows 10 1903 or higher<br/>
ARM64 -  Windows 10 2004 or higher

## Pre-setup

First we have to enable features which are required by wsl.
Open <b>Control Panel</b> and the click on <b>Programs</b> and then <b>Programs and Features</b>
On the left pane click <b>Turn Windwos Features On or Off</b>.
<br/><br/>
`Control Panel>Programs>Programs and Features`
<br/><br/>
Enable `Virtual Machine Platform` and `Windows Subsystem for Linux` by checking the boxes in front of them.<br/>
Restart your system after enabling them.<br/>
You can also enable this features from Powershell, just open Powershell as Admininstrator and type command given below.
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
![image1](https://raw.githubusercontent.com/hnccbits/cdn/master/images/learn/linux/wsl/SharedScreenshot.jpg)<br/><br/><br/>
Restart you system after the installation is complete.

## Setup
#### Update to WSL2
Now we can we move to install a linux distro to use but before that you can install <b>WSL 2</b> to get extra features and system stability.
To update to wsl 2 we have to install a file.
Download the file from the given link.<br/>

<a href="https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi">Download Kernel for WSL 2 </a>
<br/>

After installing open Powershell and type the following command:
```
wsl --set-default-version 2
```
Check wsl commands by typing:
```
wsl --help
```
If you don't want to update to <b>wsl 2</b> and instead want to keep <b>wsl 1</b> skip the above step.
#### Opening your Distro
Now go to Microsoft Store and download a linux distro of your choice.Simply search for <b>`wsl`</b> program by clicking on start menu 
and open it or by typing <b>`wsl`</b> command in Powershell. A bash like terminal will open with first time setup for username and password. After completing the setup you are good to go. 
Use as you wish install,update,upgrade various packages.Currently there is no gui but you can easily install your favourite desktop enviornment and gui support.
 I will cover this topic in later topic. 
## For Developers

As no gui is available, developers will face difficulty using. Yes there there are cli editors such as nano and vim are present but are diffcult to learn and does not provide features which are provided by IDE or even gui editors. <b>Visual Studio Code</b> comes to resuce it comes with WSL Remote Support so you just have to install Visual Studio Code in your Windwos OS.<br/>
Download Page:<br/>
<a href="https://code.visualstudio.com/">Visual Studio Code</a>
<br/>
Once the installation is complete open your linux distro and type following command : 
```
code
```
Installation of VS Code will take place. Make sure you have a active internet connection.
After installation VS Code will open. It will request to install a extension <b>Remote-WSl</b> accept the request and it will install the extension.
You can also manually install the extension.
Now you can do your projects inside your distro.
![image 2](https://raw.githubusercontent.com/hnccbits/cdn/master/images/learn/linux/wsl/SharedScreenshot1.jpg)<br/><br/>
<b>Docker</b> support is also available if you want a container to test apps.<br/>
<b>Nvidia CUDA</b> support for Machine Learning enthusiast( <a href="https://docs.microsoft.com/en-us/windows/win32/direct3d12/gpu-cuda-in-wsl">Check installation guide</a>, wsl 2 only)

## Full GUI Experience

Before we move you must know that using a GUI desktop enviornment will decrease the perfromance of the system as it is bascially virtualisation of linux enviornment under windows.

#### Method 1 (Using XRDP)
XRDP utilizes remote desktop connection of windows to display your Linux GUI
Open your linux terminal.
Type the following command to update your distro:
```
sudo apt update && sudo apt -y upgrade
```
Now we have to install xrdp:
```
sudo apt install xrdp
```
After the installation we have download a desktop enviornment. We will install a lightweight desktop enviornment <b>XFCE4</b>.
```
sudo apt install xfce4
```
To install XFCE4 Goodies / extra packages like wallpapers and applications
```
sudo apt install xfce4-goodies
```
Configure the XRDP:
```
sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
```
Now we are going to create an alias to our command which we will use to to start our remote desktop connection.
First go to home directory
```
cd ~
```
Open .bash_aliases file
```
sudo nano .bash_aliases
``` 
Create a alias by any name (I am using Kali)
```
alias kaligui="sudo /etc/init.d/xrdp"
```
Now to start the xrdp just type:
```
kaligui start
```
And Click on Start on Windows Taskbar and Type <b>Remote Desktop Connection</b>. Open it in place of commuter name type <b>`localhost:3390`</b>
and in place of username type your linux distro username. When asked for password type the password of your linux distro.


#### Method 2 (X Server)
Open linux terminal nad update your distro :
```
sudo apt update && sudo apt -y upgrade
```
Now head to SourgeForge and download <a href="https://sourceforge.net/projects/vcxsrv/files/latest/download">VcXsrv for Windows</a>(other option : Xming for Windows).
VcXsrv will be our X server utlility which will help us to display the Linux GUI enviornment.
Install the downloaded application.<br/>
Launch the apllication and set the configuration as  given in the images below:
![imag-v1](https://github.com/hnccbits/cdn/blob/master/images/learn/linux/wsl/v1.jpg?raw=true)<br/>
![image-v2](https://github.com/hnccbits/cdn/blob/master/images/learn/linux/wsl/v2.jpg?raw=true)<br/>
![image-v3](https://github.com/hnccbits/cdn/blob/master/images/learn/linux/wsl/v3.jpg?raw=true)<br/>
<br/> Finish the configuration. Don't exit the application it needs to be in background whenever you launch any GUI application.
<br/>Now we have download to our desktop enviornment.
```
sudo apt install xfce4 xfce4-goodies
```
We will create a alias
```
#Home Directory
cd ~
#Open .bash_aliases
sudo nano .bash_aliases
#Create alias
alias xgui="export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0"
```
You can also add the following command to .bashrc if you dont want to create a alias and type it every time:
```
export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
```
We will launch our launch desktop enviornment now. X server ultility which we have downloaded must be also running and properly configured.
```
xgui
startxfce4
```
You can also launch a individual program rather than opening a full linux desktop which is not possible with <b>Method 1</b>.
Just launch the GUI program as you launch any program from cli.
```
sudo program-name
```

<b>Method 2</b> is better than <b>Method 1</b> because of performance issue and also you can launch individual program rather than entier enviornment.Also if you want you can use both methods simuntaneously.
![image-f](https://github.com/hnccbits/cdn/blob/master/images/learn/linux/wsl/Screenshot_2020-09-23_16-49-05.png?raw=true)

## Extras
By default Linux Ditro installs only in drive where windows is installed. Changing the App installed location from Settings doesn't do anything.
You have to manually download appx package for your distro.
Extract in your preffered drive and click on <b>`.exe`</b> file to install.<br/>

>* [UbuntuX64-20.04](https://aka.ms/wslubuntu2004)
>* [Ubuntu-ARM-20.04](https://aka.ms/wslubuntu2004arm) 
>* [UbuntuX64-18.04](https://aka.ms/wsl-ubuntu-1804)
>* [Ubuntu-ARM-18.04](https://aka.ms/wsl-ubuntu-1804-arm) 
>* [Ubuntu-16.04](https://aka.ms/wsl-ubuntu-1604)
>* [Kali Linux](https://aka.ms/wsl-kali-linux-new) 
>* [Debian](https://aka.ms/wsl-debian-gnulinux)
>* [OpenSUSE Leap 42](https://aka.ms/wsl-debian-gnulinux)
>* [SUSE Linux Enterprise](https://aka.ms/wsl-sles-12)
>* [Fedora Remix](https://github.com/WhitewaterFoundry/WSLFedoraRemix/releases/)
>* [Arch Linux(UnOfficial)](https://github.com/yuk7/ArchWSL)

You can launch windows file explorer from bash terminal without setting up for GUI. Just type the following command:
```
explorer.exe .
```
My Terminal Setup
>- Hyper Terminal
>- Dracula Theme
>- ohmyzsh
>- Hyper Startup Plugin

