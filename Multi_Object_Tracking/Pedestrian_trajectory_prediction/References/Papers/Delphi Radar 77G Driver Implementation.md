# Delphi Radar 77G Driver Implementation

The implementation can be divided into two parts, one is the Kvaser Driver installation, another one is Delphi Driver installation. **<u>User need connect to VPN!!!!</u>**

# Kvaser Driver Installation
A PPA (Personal Package Archive) is now available for Ubuntu 16.04+ to install Kvaser Linuxcan as a DKMS (Dynamic Kernel Module System) module. This saves you from having to rebuild/fix linuxcan after every new kernel upgrade. To install the PPA, do the following:

```
sudo apt-add-repository ppa:astuff/kvaser-linux
sudo apt-get update
sudo apt-get install kvaser-canlib-dev kvaser-drivers-dkms
```

After a reboot, linuxcan should work as before and automatically re-build on a new kernel install. New versions will become available on this PPA as they are released by Kvaser.

Used when configuring a driver launch file to work with a specific Kvaser interface.

1. Verify that Kvaser Linuxcan SDK has been installed in /usr/src/

2. Reboot to load the necessary modules.

3. cd /usr/doc/canlib/examples

4. ./listChannels
	The output should look similar to:
    ```
    CANlib version 5.30
    Found 4 channel(s).
    ch  0: Kvaser USBcan Light 4xHS 73-30130-00831-1, s/n 10761, v3.9.467  (mhydra v8.30.995)
    ch  1: Kvaser USBcan Light 4xHS 73-30130-00831-1, s/n 10761, v3.9.467  (mhydra v8.30.995)
    ```
	
	For our Kvaser, it will find just 1 channel (ch 0) with serial number 28781.
	
5. The number following the "s/n" in each of these lines is the CAN Hardware ID (serial number).

6. The CAN Circuit ID is the 0-based index of the channel that you're using on a specific piece of hardware. For example, the first channel listed here would be CAN Circuit ID 0 and the 2nd would be CAN Circuit ID 1. This ordering starts over for each piece of hardware. If there were two more channels here on another Kvaser USBcan Pro, they would also be CAN Circuit ID 0 and 1 respectively.

7. Edit the launch file for the hardware you are attempting to interface with using the values you got above for the CAN Hardware ID and CAN Circuit ID.


    sudo gedit /opt/ros/kinetic/share/delphi_esr/launch/delphi_esr.launch

User needs change the arguments "use_kvaser", "kvaser_circuit_id" and "kvaser_hardware_id".

# Delphi Driver installation

1. `sudo apt update && sudo apt install apt-transport-https`

2. `sudo sh -c 'echo "deb [trusted=yes] https://s3.amazonaws.com/autonomoustuff-repo/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/autonomoustuff-public.list'`

3. `sudo apt update`

4. Once you've updated apt, you can install any of the ROS binary drivers with:

   a. `sudo apt install ros-$ROS_DISTRO-<driver_name>`
   b. Where <driver_name>  is replaced with the ROS package name of the driver (e.g. delphi-esr, mobileye-560-660, neobotix-usboard, etc).

5. When you run `sudo apt update` and `sudo apt upgrade`, new versions of the drivers will be downloaded and installed automatically.

6. The following command will install all available drivers from AutonomouStuff:

   a. `sudo apt install ros-$ROS_DISTRO-kvaser-interface ros-$ROS_DISTRO-delphi-esr ros-$ROS_DISTRO-delphi-srr ros-$ROS_DISTRO-kartech-linear-actuator ros-$ROS_DISTRO-mobileye-560-660 ros-$ROS_DISTRO-neobotix-usboard ros-$ROS_DISTRO-ibeo-lux`
b. If PACMod is needed: `sudo apt-get install ros-$ROS_DISTRO-pacmod ros-$ROS_DISTRO-pacmod3 ros-$ROS_DISTRO-pacmod-game-control`