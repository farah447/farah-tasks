# farah-tasks
algorthim for installing ROS on ubuntu:
# first download ubuntu on virtualBox:

step 1: Go to VirtualBox website here to download the binary for your current operating system. 
step 2:  When download is finished, run the executable file. Continue with the installation of VirtualBox with the defaults.
This will open VirtualBox at the end of the installation.
step 3: Create Virtual Machine. Click 'New' button to open a dialog.
step 4: Type a name for the new virtual machine. Note that VirtualBox automatically changes 'Type' to Linux and 'Version' to 'Ubuntu (64 bit)'.
These two options are exactly what we need.
step 5: memory size depends on your host machine memory size. make sure it is large enough since the hard drive will be splitted into root (/)and swap partitions.
step 6: Accept the default 'Create a virtual hard drive now' and click 'Create' button.
step 7: Continue to accept the default 'VDI' drive file type and click 'Next' button.
step 8: Change the storage type from the default 'Dynamically allocated' to 'Fixed size' to increase performance.
step 9: For the virtual hard drive space, the default value is 8GB.
step 10: Click 'Create' button and VirtualBox will generate Ubuntu virtual machine.
step 11: Now the virtual machine is created. We are ready to install Ubuntu in this virtual machine.
Select your new virtual machine and click 'Settings' button.
step 12: Click on 'Storage' category and then 'Empty' under Controller:IDE. Click "CD/DVD" icon on right hand side and select the ubuntu ISO file to mount.
step 13: You can change processors number by clicking on 'System' category. change the number of CPUs to 4 since 4 is the largest value shown on the green bar. 
Now you can click 'OK' button to continue.
step 14: VirtualBox may pop up a message about 'Auto capture keyboard' option. Read the message there and check 'Do not show this message again' option before clicking OK.
step 15: Install Ubuntu, Back to Oracle VM VirtualBox Manager, click on the new Ubuntu virtual machine and hit 'Start' button.
Now you shall see a 'Welcome' screen. Click 'Install Ubuntu' button. Note that the installation process may differ a little bit from version to version.
step 16: Click 'Continue' button.
step 17: Make sure 'Erase disk and install Ubuntu' option is selected and click 'Install Now' button.
step 18: Ubuntu will ask you a few questions. If the default is good, click 'Continue' button.
step 19: In 'Who are you?' dialog, enter your preferred name, username and password. Note that this user will have root/sudo privilege. Click 'Continue' button.
step 20: The installation will continue until it is finished.
step 21: After installation is complete, click 'Restart Now' button. When you see a screen with a black background saying 'Please remove installation media and close the tray (if any) then press ENTER:', just follow it.
step 22: Enter the password you have chosen and press 'Enter'.
step 23:The Ubuntu Desktop OS is ready. 

# second download ROS on ubuntu:

1- Setup your computer to accept software from packages.ros.org.

     sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

2- Set up your keys

     sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

3- Installation. First, make sure your Debian package index is up-to-date:

     sudo apt update

Now pick how much of ROS you would like to install.

Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages

     sudo apt install ros-noetic-desktop-full
     
Desktop Install: Everything in ROS-Base plus tools like rqt and rviz

     sudo apt install ros-noetic-desktop
     
ROS-Base: (Bare Bones) ROS packaging, build, and communication libraries. No GUI tools.

     sudo apt install ros-noetic-ros-base

4- Environment setup, You must source this script in every bash terminal you use ROS in.

     source /opt/ros/noetic/setup.bash
     
It can be convenient to automatically source this script every time a new shell is launched. These commands will do that for you.
Bash

     echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

zsh

     echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc

5- Dependencies for building packages

To install this tool and other dependencies for building ROS packages, run:

     sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
Initialize rosdep

     sudo apt install python3-rosdep

With the following, you can initialize rosdep.

     sudo rosdep init
rosdep update

#done.
