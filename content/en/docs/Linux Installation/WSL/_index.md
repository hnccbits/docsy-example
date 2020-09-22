
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
![image1](https://raw.githubusercontent.com/moonstoper/cdn/master/images/learn/linux/wsl/SharedScreenshot.jpg)<br/>
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
Download Page<br/>
<a href="https://code.visualstudio.com/">Visual Studio Code</a>
<br/>
Once the installation is complete open your linux distro and type following command : 
```
code
```
Installation of vscode will take place .Make sure you have a active internet connection.
After installation VS Code will open. It will request to install a extension <b>Remote-WSl</b> accept the request and it will install the extension.
You can also manually install the extension.
Now you can do your projects inside your distro.
![image 2](https://raw.githubusercontent.com/moonstoper/cdn/master/images/learn/linux/wsl/SharedScreenshot1.jpg)
<b>Docker</b> support is also available if you want a container to test apps.<br/>
<b>Nvidia CUDA</b> support for Machine Learning enthusiast( <a href="https://docs.microsoft.com/en-us/windows/win32/direct3d12/gpu-cuda-in-wsl">Check installation guide</a>, wsl 2 only)



