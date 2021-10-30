

UMBC Energy Efficient High Performance Computing Lab

Faculty: [Tinoosh](mailto:tinoosh@umbc.edu)[ ](mailto:tinoosh@umbc.edu)[Mohsenin](mailto:tinoosh@umbc.edu)[ ](mailto:tinoosh@umbc.edu)(<tinoosh@umbc.edu>)

Author: [Kamran](mailto:katara1@umbc.edu)[ ](mailto:katara1@umbc.edu)[Ataran](mailto:katara1@umbc.edu)[ ](mailto:katara1@umbc.edu)[Rezai](mailto:katara1@umbc.edu)[ ](mailto:katara1@umbc.edu)(<katara1@umbc.edu>)

\*The following guide is a detail regarding the main general guide of “Getting started with the

lighthouse system”:

[https://www.bitcraze.io/documentation/tutorials/getting-started-with-lighthouse](https://www.bitcraze.io/documentation/tutorials/getting-started-with-lighthouse/)[/](https://www.bitcraze.io/documentation/tutorials/getting-started-with-lighthouse/)

Hardware Dependencies:

Device(s)

Link(s)

Crazyflie 2.1

[https://store.bitcraze.io/collections/kits/products](https://store.bitcraze.io/collections/kits/products/crazyflie-2-1)[/](https://store.bitcraze.io/collections/kits/products/crazyflie-2-1)

[crazyflie-2-1](https://store.bitcraze.io/collections/kits/products/crazyflie-2-1)

Lighthouse Positioning Deck

Crazyradio PA 2.4 GHz USB Dongle

Lighthouse V2 base stations

[https://store.bitcraze.io/products/lighthouse-posit](https://store.bitcraze.io/products/lighthouse-positioning-deck)

[ioning-deck](https://store.bitcraze.io/products/lighthouse-positioning-deck)

[https://store.bitcraze.io/collections/kits/products](https://store.bitcraze.io/collections/kits/products/crazyradio-pa)[/](https://store.bitcraze.io/collections/kits/products/crazyradio-pa)

[crazyradio-pa](https://store.bitcraze.io/collections/kits/products/crazyradio-pa)

[https://store.bitcraze.io/collections/accessories/pr](https://store.bitcraze.io/collections/accessories/products/lighthouse-v2-base-station)

[oducts/lighthouse-v2-base-station](https://store.bitcraze.io/collections/accessories/products/lighthouse-v2-base-station)

Software Dependencies:

Name(s)

Instruction(s)

bitcraze/crazyflie-lib-python

[https://github.com/bitcraze/crazyflie-lib-pytho](https://github.com/bitcraze/crazyflie-lib-python/blob/master/docs/installation/install.md)

[n/blob/master/docs/installation/install.md](https://github.com/bitcraze/crazyflie-lib-python/blob/master/docs/installation/install.md)

bitcraze/crazyflie-clients-python

[https://github.com/bitcraze/crazyflie-clients-p](https://github.com/bitcraze/crazyflie-clients-python/blob/master/docs/installation/install.md)

[ython/blob/master/docs/installation/install.md](https://github.com/bitcraze/crazyflie-clients-python/blob/master/docs/installation/install.md)





python3

pip3

[https://phoenixnap.com/kb/how-to-install-pyt](https://phoenixnap.com/kb/how-to-install-python-3-ubuntu)

[hon-3-ubuntu](https://phoenixnap.com/kb/how-to-install-python-3-ubuntu)

[https://www.educative.io/edpresso/installing-p](https://www.educative.io/edpresso/installing-pip3-in-ubuntu)

[ip3-in-ubuntu](https://www.educative.io/edpresso/installing-pip3-in-ubuntu)

Setup:

**Ubuntu 21.04 / 20.04.3 LTS**

As of writing this manual, the most recent version of Ubuntu is 21.04. It is recommended to use

the latest version of Ubuntu while working with the Crazyflie Lighthouse system. There is also

the option of a Bitcraze virtual machine with a given installation guide. However, linux works

faster and is more reliable compared to the VM.

**Python3 & Pip3**

Install the most recent version of python using the link provided above. I have worked with

python3 and pip3 for most of my package installations and they are more recent compared to

python and pip. However, it is not required to install the most recent version of either python or

pip using the given links.

**Crazyflie Python Library**

The demos available for the lighthouse deck are within the python library of crazyflie which can

be used to fly the drones in any desired pattern. The library needs to be cloned and installed

using the given link above. It is recommended to use the python library examples for the *first*

*time* users of the lighthouse deck. The main example codes that are using the lighthouse are the

swarm sequences provided by default.

**Crazyflie Clients Python**

The installation of this repository is a **must** in order to access the lighthouse tab under the

Crazyflie PC Client also known as “cfclient”. When everything is cloned and installed using the

link provided (which also prompts you to upgrade python and pip), a terminal would need to be

opened from the installation location which then accepts the command “cfclient” for accessing

the detailed Crazyflie PC client. Note: crazyradio driver installation is not necessary for linux





systems but the instructions from the crazyflie-python-lib are needed for getting USB permission

to work with the **crazyradio PA**.

**V2/V1 Base Stations**

The base stations are the crucial part of working with the lighthouse decks. The Bitcraze tutorial

website explains in detail how to set up the base stations. For V1, the “Set BS Channel” under

system management of cf client's Lighthouse Positioning tab is not used. That specific window is

only for **V2 base stations**! As mentioned on the website, each V2 BS needs to be connected once

to a computer for getting set to appropriate channels and then disconnected. This process does

not need to happen every time the V2 BS is turned on. For V1 BS, there is a button on the back

which helps to set the channels based on the cables available with the purchased station. Make

sure to mount the base stations (V2/V1) on camera stands or walls with the mentioned height and

tilt for detection and accuracy. The lights on top of each BS should turn green once they are able

to detect each other. Note: There is a distance advantage when using V2 BS in comparison to V1

BS for any trial.

**Preparing the Crazyflie**

Using the installed cfclient and crazyradio PA, connect to the drone with the lighthouse deck

installed on top. The radio needs to be in 2Mbit mode. Using the radio connection, go to the

“Connect” and click on “Bootloader” and a new window will open. While connected to the

radio, choose the most recent package to flash on the “From release” tab. Then click on

“Program” and wait for the drone to be updated along with the lighthouse deck. Now, it is ready

for calibration. Go back to the Lighthouse Positioning tab and choose the BS type from “Change

system type”. If the base stations are ready and set, the drone should start to **receive** sweeping

angles from the stations automatically and **calibrate** its location. If both of those have finished

and turned green, click on “Manage geometry” and select “Estimate Geometry”. Make sure the

new BS locations make sense and proceed by choosing “Write to Crazyflie”. The 3D view on

your current tab should now show the drone as a blue dot in center and base stations as 1 and 2

on either side of the drone. Both **geometry** and **estimator** should now be green. Check the

positioning of the drone by moving it around while looking over the 3D view. The drone is now

ready to fly! In order to fly the drone, disconnect from the cfclient and on a terminal type the

following:

*python3 name\_of\_the\_example\_program.py*

Note: The geometry will need to be set again if the crazyflies have been reset. Also, the code can

be run in **Visual Studio** by opening the code and pressing the green arrow on top right of the

window.





Probable hardware/software issues:

**Base Stations**

If the crazyflie detects the base stations at a very close proximity to itself, do **NOT** fly the drone.

Make sure the base stations are located at a good distance away from it and keep resetting the

geometry until the 3D view shows a good distance from them and the drone. Otherwise, there is

a high chance that the drone will crash.

**Lighthouse Deck**

At some point during the trials, there may be an issue with detecting the sweeping angles. The

drone tends to keep resetting by itself when in range of two base stations and M1 LED will blink

at a fast pace. There is a manual fix for this issue discussed in the Bitcraze forum. First, turn on

the V2/V1 BS and set them to appropriate channels. Then, hide the drone from the base stations

and press “change system type” on the lighthouse positioning tab on cfclient. Change the system

to V2/V1 and back to V1/V2. This resets the previous geometry calibrations of the Crazyflie and

thus there will be no more refreshing when the two base stations are detected! Now, connect to

the crazyflie and, if on appropriate BS channels, they will automatically receive and calibrate.

All that needs to be done now is setting the geometry to new values and testing the drones.

**Additional Information**

If additional issues are preventing the drone from flying (lighthouse questions included), please

visit the following FAQ for detailed answers:

[https://docs.google.com/document/d/19whW8Vf5ssbnM-swZKMQ7Yxf4S9kWOW-Az9zb7Fkil](https://docs.google.com/document/d/19whW8Vf5ssbnM-swZKMQ7Yxf4S9kWOW-Az9zb7Fkilo/edit?usp=sharing)

[o/edit?usp=sharing](https://docs.google.com/document/d/19whW8Vf5ssbnM-swZKMQ7Yxf4S9kWOW-Az9zb7Fkilo/edit?usp=sharing)

