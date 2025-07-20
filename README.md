# ChromeOS

<img width="961" height="960" alt="66d67304d278d-ChromeOS" src="https://github.com/user-attachments/assets/d491c351-cac9-4b19-84fa-64dcdb4a8292" />


Have you ever wanted to experience ChromeOS on your hardware? well.. the https://github.com/sebanc/brunch framework does just that! it patches the initial ChromeOS package. so, i'm gonna show it to you how to do it! Now assuming you don't wanna dual boot and your using Windows, you need a 16 GB USB or larger. you can use the guide below:

# Guide for Intel CPU users:

Well, You gotta see what your CPU architecture is. to see that, if your on windows. go to windows task manager. if not, you can search it on google on how to find your architecture. then go to the performance tab, on the right side of the corner, you can see your Architecture! Be sure to download the latest ChromeOS recovery image.

for 8th gen & 9th gen: "shyvana" recovery image is the most stable, you can get the recovery image from here: https://cros.tech/device/shyvana/.
for 10th gen: "jinlon" recovery image is most stable, you can get the recovery image from here: https://cros.tech/device/jinlon/.
for 11th gen & above: "voxel" recovery image is most stable, you can get the recovery image from here: https://cros.tech/device/voxel/.


# Step 1. Gather files.

You now need to download the LATEST version of brunch. the brunch file is the one to patch the chromeos recovery image, you can get it from here: https://github.com/sebanc/brunch/releases/latest.

then place the chromeOS recovery image and the brunch patcher image to a temporary place that has atleast 42 GB of storage. it is recommended for the temporary place to not have anything other than the chromeOS recovery image and brunch file.

# Step 2. Windows Subsystem for Linux (WSL).

You need to first search up "Turn windows features on or off", and open it, then select "Windows Subsystem For Linux". and install it, if it asks to reboot, reboot. after booting back up, open Windows Powershell as Administrator. then run the command "wsl --install". then wait for it to download and install it. then when its finished, there should be a new app called "Ubuntu". no, your not gonna install Linux, so dont be scared as that is just a Virtual Machine for Linux. now open "Ubuntu". now assuming you placed the chromeOS recovery files and brunch files onto the D:\ Drive in Windows, you need to use these commands in the Ubuntu Virtual Machine Terminal. First Command: "sudo add-apt-repository universe", next command "sudo apt update && sudo apt -y install pv cgpt tar unzip". next assuming you placed the files in the root of the D:\ Drive, use "cd /mnt/d" command. then go to Windows Explorer, then extract Brunch recovery image, then there should be another image in the extracted folder, extract that image too, then copy the rootc.img and efi_secure.img and efi_legacy.img and chromeos-install.sh onto the root of the D:\ drive, then extract the chromeOS recovery image, then rename the .bin file to chromeos.bin. then copy the renamed chromeOS .bin onto the root of the D:\ drive. now onto the Ubuntu Terminal again, do another command, the command is "sudo bash chromeos-install.sh -src chromeos.bin -dst chromeos.img". then type "yes" if it asks for confirmation. it can take some time, the minimum time is 27 minutes. wait, The installation will report that ChromeOS was installed when it is finished. Before closing the terminal, make sure that there are no additional errors in the terminal. If there are no errors, then you are good to go!

# Step 3. Flashing the Image.

Here comes the USB Drive part. make sure your USB has atleast 16-17 GB of storage. then download rufus from rufus.ie. then flash the "chromeos.img" from the root of the D:\ drive on the USB drive.

# Step 4. Booting Into ChromeOS with USB (temporarily).

Go through the setup normally as if like a normal Chromebook. but when the option to use a account, select the "Browse as Guest" or something like that. then after seeing the desktop. switch to the TTY2 terminal with Ctrl + Alt + F2, then login as root. then use this command "lsblk -e7", this will show all disks, find your internal drive, lets assume your internal drive is /dev/nvme0n1, then you gotta use this command, "chromeos-install -dst (YOUR INTERNAL DRIVE!, DONT CHOOSE OTHER DRIVES!!!!), the installation may ask for confirmation, type yes into the prompt. the installation may take some time, please wait. The installation will say that ChromeOS was installed when it is finished. Before closing the terminal, make sure that there are no errors in the terminal. If there are no errors, then good to go!, the installation is finished, though it is recommended to follow the below instructions too.

# Next Steps after first boot.

It is normal for the first boot to take some time. and seeing "Loading Brunch Framework" and "Rebuilding RootFS" and other stuff. after that, when you see the "Welcome to your chromebook", you can unplug your USB drive.


# Done!

Your done! Have fun! Good luck!


# Credits:

Google for ChromeOS,

Sebanc for the Brunch Framework.



