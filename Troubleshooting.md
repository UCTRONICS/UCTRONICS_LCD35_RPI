# If you have any problems, please feel free to contact us and we will try our best to help you.

# Q1:Some zones working much better than others, the near edge zones seem the worst.
 
You should recalibrate the touchscreen. 

- 1.Downloading our UCTRONICS_LCD35_HDMI_RPI package from https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI.git

- 2.Install calibration software for calibration

  - 2.1 cd UCTRONICS_LCD35_RPI
  
  - 2.2 sudo unzip Xinput-calibrator_0.7.5-1_armhf.zip
  
  - 2.3. cd xinput-calibrator_0.7.5-1_armhf/
  
  - 2.4. sudo dpkg -i -B xinput-calibrator_0.7.5-1_armhf.deb
  
  ![Alt text](https://github.com/UCTRONICS/UCTRONICS_LCD35_HDMI_RPI/blob/master/image/1.jpeg)
  ![Alt text](https://github.com/UCTRONICS/UCTRONICS_LCD35_HDMI_RPI/blob/master/image/2.jpeg)
  ![Alt text](https://github.com/UCTRONICS/UCTRONICS_LCD35_HDMI_RPI/blob/master/image/3.jpeg)
  ![Alt text](https://github.com/UCTRONICS/UCTRONICS_LCD35_HDMI_RPI/blob/master/image/4.jpeg)
  
 
 # Q2: How to write UCTRONICS RPI LCD3 5 Screen image to the SD card Windows?
 
 - You can refer to the below video :
 
 Image can be downloaded from http://uctronics.oss-us-west-1.aliyuncs.com/LCD35/image/UCTRONICS_LCD35_RPI.img
 
 [![IMAGE ALT TEXT](https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI/blob/master/image/5.jpeg)](https://youtu.be/cCw91wH6mnc "How to write UCTRONICS SPI LCD3 5 Screen image to the SD card Windows The Raspberry Pi Beginners Guide")

# Q3: How to install the touchscreen driver and display driver for SPI LCD35 

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

- Step4: Come in the UCTRONICS_LCD35_HDMI_RPI
```Bash
 cd UCTRONICS_LCD35_RPI
```
- Step5: Get run permissions
```Bash
sudo chmod 777 UCTRONICS_LCD_backup
```
```Bash
sudo chmod 777 UCTRONICS_LCD35_install
``
``Bash
sudo chmod 777 UCTRONICS_LCD_restore
```
```Bash
sudo chmod 777 UCTRONICS_LCD_hdmi
```

- Step6: backup data
```Bash
sudo ./UCTRONICS_LCD_backup
```
- Step7: install our UCTRONICS LCD35 RPI driver
```Bash
sudo ./UCTRONICS_LCD35_install
```
wait a while the system will be installed and restarted automatically.

if you want to reuse the pre-installation system, you can use the below command
```Bash
sudo ./UCTRONICS_LCD_restore
```
If you want to display on hdmi instead of LCD,just use the below command
```Bash
sudo ./UCTRONICS_LCD_hdmi
```
# Q8: How to burn the UCTRONICS_LCD35_RPI.img?

- Step1: Download the burn tools from https://github.com/UCTRONICS/Win32DiskImager.git 

- Step2: Download the UCTRONICS_LCD35_RPI.img file from 

 http://uctronics.oss-us-west-1.aliyuncs.com/LCD35/image/UCTRONICS_LCD35_RPI.img 

- Step3: Open the SDFormatter to format your SD card 

- Step4: Open the Win32DiskImager to write the  UCTRONICS_LCD35_RPI.img to your SD card.

 For more details please refer to our video demo from https://www.youtube.com/watch?v=cCw91wH6mnc 

# Q9: Why the HDMI display stop at rainbow ?

 After loading our LCD35 SPI driver, the system just support our LCD35 screen which means you can't use the HDMi screen.
 





 
 
 
