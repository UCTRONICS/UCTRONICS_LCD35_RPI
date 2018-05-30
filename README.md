# UCTRONICS_LCD35_RPI  (SKU: U4703)
## This driver is used for UCTRONICS LCD35 with SPI interface

##  Revision History:
- 2018-05-30 : add support rotate 0/ 90/ 180/ 270 degree

## Any problems, please refer to our troubleshootings 
- https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI/blob/master/Troubleshooting.md

## Easy Install
```Bash
wget https://raw.githubusercontent.com/UCTRONICS/UCTRONICS_LCD35_RPI/master/install
```
```Bash
sudo chmod +x install
```
```Bash
sudo ./install 

```
## Detail operations 
### Step1: Expand the sd card first
```Bash
sudo raspi-config choose Advanced Operations -> Expand Filesystem 
```
```Bash
sudo reboot
```
### Step2: Update your raspberry pi system
```Bash
 sudo apt-get update
```
### Step3: Download the driver package
```Bash
 sudo git clone https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI.git
```
 ![EasyBehavior](https://github.com/UCTRONICS/pic/blob/master/gif/download.gif) 
### Step4: Come in the UCTRONICS_LCD35_RPI
```Bash
 cd UCTRONICS_LCD35_RPI
```
 ![EasyBehavior](https://github.com/UCTRONICS/pic/blob/master/gif/cd_uctronics_lcd35_rpi.gif) 
### Step5: Get run permissions
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
 ![EasyBehavior](https://github.com/UCTRONICS/pic/blob/master/gif/change_permission.gif) 
 
### Step6: backup data
```Bash
 sudo ./UCTRONICS_LCD_backup
``` 
 ![EasyBehavior](https://github.com/UCTRONICS/pic/blob/master/gif/backup.gif) 
 
### Step7: install the LCD35 driver
```Bash
 sudo ./UCTRONICS_LCD35_install
``` 
 ![EasyBehavior](https://github.com/UCTRONICS/pic/blob/master/gif/install_lcd35.gif) 
 
 wait a while the system will be installed and restarted automatically.
 
 ### Reuse the pre-installation system
```Bash
 sudo ./UCTRONICS_LCD_restore
```
 ### display on hdmi 
```Bash 
   sudo ./UCTRONICS_LCD_hdmi
```
## Add more functions for the LCD :
 ### NO1. Install calibration software for calibration
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

### NO2. Install virtual keyboard

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
 
## Add new ICON to desktop ?

### If it's just a folder, add it directly to the desktop

### If it is an executable, follow this steps:

* step1: choose the Directory Tree -> / -> usr -> share ->applications folder

* Step2: choose a icon you want to link 

* Step3: choose edit -> create link... ->Desktop ->OK

## Rotate the screen to 0/90/180/270 degree
```Bash
cd ~UCTRONICS_LCD35_RPI
```
- For rotate 0 ：
```Bash
             sudo chmod +x UCTRONICS_LCD35_install
             sudo ./UCTRONICS_LCD35_install 
```

- For rotate 90 ：
```Bash
            sudo chmod +x UCTRONICS_LCD35_rotation_90_install 
            sudo ./UCTRONICS_LCD35_rotation_90_install 
```
For rotate 180 ：
```Bash
            sudo chmod +x UCTRONICS_LCD35_rotation_180_install 
            sudo ./UCTRONICS_LCD35_rotation_180_install
```
For rotate 270 ：
```Bash
            sudo chmod +x UCTRONICS_LCD35_rotation_270_install 
            sudo ./UCTRONICS_LCD35_rotation_270_install
```

### Rotation =0
![Alt text](https://github.com/UCTRONICS/pic/blob/master/LCD35_SPI_0.jpg)
### Rotation =180
![Alt text](https://github.com/UCTRONICS/pic/blob/master/LCD35_SPI_180.jpg)





