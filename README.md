# UCTRONICS_LCD35_RPI  (SKU: U4703)
# This driver is used for LCD35 with SPI interface
# Any problems, please refer to our troubleshootings 

### https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI/blob/master/Troubleshooting.md

### Install the UCTRONICS_LCD35_RPI is very easy.<br>
 ### Just run 
```Bash
wget https://raw.githubusercontent.com/UCTRONICS/UCTRONICS_LCD35_RPI/master/install
```
```Bash
sudo chmod +x install
```
```Bash
sudo ./install 
```
### If you want to know the detail  operations see the follows.

### This driver package is used for UCTRONICS 3.5 inches LCD which can run on Raspbery Pi zero Pi2 Pi3 Model B/B+ paltforms.

### In order to use it easier,we provide you operation steps in detail. 

- Step1: Expand the sd card first
```Bash
sudo raspi-config choose Advanced Operations -> Expand Filesystem 
```
```Bash
sudo reboot
```
- Step2: Update your raspberry pi system
```Bash
 sudo apt-get update
```
- Step3: Download the driver package
```Bash
 sudo git clone https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI.git
```
- Step4: Come in the UCTRONICS_LCD35_RPI
```Bash
 cd UCTRONICS_LCD35_RPI
```
- Step5: Get run permissions
```Bash
 sudo chmod 777 UCTRONICS_LCD_backup
```
```Bash
 sudo chmod 777 UCTRONICS_LCD35_install
```
```Bash
 sudo chmod 777 UCTRONICS_LCD_restore
```
```Bash
 sudo chmod 777 UCTRONICS_LCD_hdmi
 ```
- Step6: backup data
```Bash
 sudo ./UCTRONICS_LCD_backup
``` 
- Step7: install the LCD35 driver
```Bash
 sudo ./UCTRONICS_LCD35_install
``` 
### wait a while the system will be installed and restarted automatically.<br>
### if you want to reuse the pre-installation system, you can use the below command
```Bash
 sudo ./UCTRONICS_LCD_restore
```
 ### If you want to display on hdmi instead of LCD,just use the below command
```Bash 
   sudo ./UCTRONICS_LCD_hdmi
```
### Add more functions for the LCD :
 
 - NO1. Install calibration software for calibration
```Bash 
  cd UCTRONICS_LCD35_RPI
```
```Bash
  sudo unzip Xinput-calibrator_0.7.5-1_armhf.zip 
```
```Bash
  cd xinput-calibrator_0.7.5-1_armhf/
```
```Bash
  sudo dpkg -i -B xinput-calibrator_0.7.5-1_armhf.deb
```

- NO2. Install virtual keyboard

- 1. Execute the following commands to install the corresponding software
```Bash
 sudo apt-get update
```
```Bash
 sudo apt-get install matchbox-keyboard
```
```Bash
 sudo nano /usr/bin/toggle-matchbox-keyboard.sh
```
- 2. Copy the following contents to toggle box - keyboard. Sh, save the exit
```Bash
  #!/bin/bash
   #This script toggle the virtual keyboard
   PID=`pidof matchbox-keyboard`
  if [ ! -e $PID ]; then
   killall matchbox-keyboard
   else
   matchbox-keyboard -s 50 extended&
   fi
```
- 3. Execute the following command
```Bash
sudo chmod +x /usr/bin/toggle-matchbox-keyboard.sh
```
```Bash
sudo mkdir /usr/local/share/applications
```
```Bash
sudo nano /usr/local/share/applications/toggle-matchbox-keyboard.desktop
```
- 4. Copy the following contents to toggle - matchbox - keyboard. Desktop, save exit 
```Bash
[Desktop Entry]
Name=Toggle Matchbox Keyboard 
Comment=Toggle Matchbox Keyboard` 
Exec=toggle-matchbox-keyboard.sh
Type=Application
Icon=matchbox-keyboard.png
Categories=Panel;Utility;MB
X-MB-INPUT-MECHANSIM=True
``` 
- 5. To perform the following command, note that this step must use the "PI" user permission, and if the administrator privileges are used, the file will not be found
```Bash
nano ~/.config/lxpanel/LXDE-pi/panels/panel
``` 

 - 6. Find similar commands (different versions of ICONS may differ)
 ```Bash
 Plugin {
 type = launchbar
 Config {
 Button {
 id=lxde-screenlock.desktop
 }
 Button {
id=lxde-logout.desktop 
  }
 }
```
- 7. Add the following code to add a Button item
```Bash
 Button {
 id=/usr/local/share/applications/toggle-matchbox-keyboard.desktop
  }
 ```
- 8. To restart the system with the following command, you can see a virtual keyboard icon in the top left corner
```Bash
  sudo reboot
```
 
- NO3. How to add new ICON to desktop ?

### If it's just a folder, add it directly to the desktop

### If it is an executable, follow this steps:

* step1: choose the Directory Tree -> / -> usr -> share ->applications folder

* Step2: choose a icon you want to link 

* Step3: choose edit -> create link... ->Desktop ->OK

- NO4. How to rotate the screen to 180 degree ?
```Bash
cd UCTRONICS_LCD35_RPI
```
```Bash
sudo chmod 777 UCTRONICS_LCD35_rotation_180_install
```
```Bash
sudo ./UCTRONICS_LCD35_rotation_180_install
```
# Rotation =0
![Alt text](https://github.com/UCTRONICS/pic/blob/master/LCD35_SPI_0.jpg)
# Rotation =180
![Alt text](https://github.com/UCTRONICS/pic/blob/master/LCD35_SPI_180.jpg)





