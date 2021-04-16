# Tech Tues Episode 1

Script for stream to be made into a repo of instructions links and such.

## Welcome People point them to repo and links ect.


## Set up Virtual machine

  - Talk about what a virtual machine is,
  - chat about different ways this could be set up
  - chat about if you arnt using a vm and that the rest of the stream is not dirivitive of useing a VM it is purely for ease of the Stream that i am doing VM
  -Chat about if they want to use WSL2 and UBUNTU then they cant do this.... see school of youtube for that.

    ### steps

    1. Download Virtual box..and Mint ISO( if you are already familiar with vms then pick your software of choice)
      here is a link (link to Virtual box)
    1. Open Oracle VM.
    1. select New button the one with the big blue explosion
    1. Title your box and select where it wants to live on your system,
    you will want to select Type of Linux and Verson of Ubuntu 64bit. if you are planing on installing mint as we are in the demo. then click next.
    1. set your mem allocation for this virtual machine. i recomned atleast 2048mb or more if useing this for development.
    1. keep the settin of create Virtual hard disk and click create this will create a virtual version of a hdd as a peramiter of the file and set it up with dedicated space or adjusting space depending on the settngs
    1. you want a VDI in most circumstances.
    1. keep dynamically allocated : this allows the vm to grow up to a cirtin size as you use it instead of taking it all at once
    1. then set how much space you want your computer to have.
    1. next we open settings and change a few things to make sure linux runs smoothly as a vm.
        - general > advanced (change shared clipboard and DnD to bidirectional to allow you to move files around eaisly between hoast and vm.... ONLY do this if you are developing Not PENTESTING OR ORTHER SECURITY THNG can be a vuln to get to your files.)
        - system > motherboard ( un check flopy and move it down , then move HD above optical.)
        - system > Processor ( up it to 2 cpus and enable PAE/NX)
        - display > screen Video Mem all the way up so that your can render your screen details well. and make sure 3D Acc is OFF
        - storage > click on the disk then on the right there is annother little disk click that and seleckt create Virtual optical Disk.
        add, and creat one for mint iso in your downloads folder. select it and close the window. now you can boot the Machine

## Install Linux Mint on New machine

- Talk about linux a bit. while workign through this seciton.
- this is a good time to talk about diferent versions of linux
- this is also a good place to chat about this being one way of many to - do this.
- Have goot time fill install takes a min or 2 and want to do whole thing live .

  ### steps

    1. boot machine
    1. select boot drive
    1. start linux mint (This boots to a graphical desktop with some icons and an install mint iso.)
    1. Runn the iso
    1. follow the insturctions provided by mint some setting you might want to change are:
        - language
        - you want Multimedia codecs this allows it to work with special media types.
        - Time zone
        - option one erase disk install mint is the opt you want
    1. set your name computer name and password and encrypt home
    1. once mint is installed reboot the Virtual machine

## Setup some basic JS develpment tools

- first steps for linux mint..
- talk about SUDO command and APT command
- talk about CURL and a few others too
- Start talking about the different softwares and settings needed to do basic development and run code.
- node
- vs code (or other code editor)
- NVM node version Manager
- tree
- eslint (spell check for code)
- getting Slack / Discord / other basic programs up.

  ### Initial linux gui steps

    1. Start in the welcome box and go to first steps pick color and theme.
    1. Open up driver manager and run the updater
    1. if not on a vm open up snapshot and set it up (this is your system backups) for a vm we will use virtual box snapshots to keep state.
    1. Turn on the UDP firewall

  ### The rest of the setup

    1. open up terminal
    1. run command `sudo apt=get update && sudo apt-get upgrade -y` (THIS WILL TAKE TIME)
    1. once fininshed run `sudo apt autoremove`
    1. now the command `sudo apt-get install build-essential -y` (this brings in some requiremnets for you system to handle code programns like node and SQL)
    1. run `curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash` to get NVM downloaded to linux and installed
    1. the last command requires us to restart terminal so do that or run `source ~/.bashrc`
    1. now we can check NVM version with `nvm --version` (should be 0.3.0 or higher)
    1. Next we use nvm to install node.js we want node 12 so use the command `nvm install 12`
    1. check that node installed right `node --version` (12.22 or highter)
    1. and you can check if node works by starting and doing some math. `node` then `num+num` if the math is right node is working
    1. You need Git to manage code repos so `sudo apt install git`
    1. we will want Tree `sudo apt install tree` lets us print grapical file trees in terminal
    1. we will want live-server to demo our website code on our system `npm install -g live-server`
    1. we will want eslint for checking our code for simple mistakes `npm install -g eslint`

  ### Git Configuration

    to customize your git config so that it works with your git hub do the following commands in order
    1. `git config --global core.editor "code --wait"`
    1. `git config --global user.name 'YOUR FULL NAME'`
    1. `git config --global user.email 'YOUR GitHub Email Address'`
    1. `git config --global core.editor "code --wait"`

  ### some Software to install and setup

    #### Chrome
    
    linux has a access to chromium from the terminal or you can go to google and download and run chrome from their site... 
    `sudo apt-get install chromium-browser`

    #### VS CODE

    like with chrome you can go hunt it down online at their site or run this command to install it from the terminal little more complex as there are dependicys but not too bad lets go

    - update the system `sudo apt update`
    - get the dependicies installed `sudo apt install software-properties-common apt-transport-https wget`
    - get the key from MS `wget -q https://packages.microsoft.com/keys/microsoft/asc -O- | sudo apt -key add -`
    - enable Vs Code REPO `sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"`
    - now install from there using `sudo apt install code`

    inside VS code you should add the following Extentions (RECOMENDATIONS FROM RAVENMOORE)
      - live server
      - ESLint
      - Markdown Lint
      - HTML Preview
      - Debugger for Chrome (SUPER TOOL)
      - terminal for Ubuntu (term inside code window)

  ### tweek terminal for dev work

  on linux mint the hidden file .bashrc controlls how your terminal works. i have some tweeks that i like to use and i have provided the file... this adds auto complete and repo finding and status.

  - first backup your current bash file.. `mv ~/.bashrc .bashrc.bak`
  - now run `code .bashrc` to open the bash file
  - you can copy the contents of template over this file and then save
  - restart terminal and you should have slightly different prompt with different or less giberish.
