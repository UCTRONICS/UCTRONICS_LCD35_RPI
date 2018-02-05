# If you have any problems, please feel free to contact us and we will try our best to help you.

# Q1:Some zones working much better than others, the near edge zones seem the worst.

A1: 
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
 
 A2:
 > You can refer to the below video :
 
 Image can be downloaded from http://uctronics.oss-us-west-1.aliyuncs.com/LCD35/image/UCTRONICS_LCD35_RPI.img
 
 [![IMAGE ALT TEXT](https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI/blob/master/image/5.jpeg)](https://youtu.be/cCw91wH6mnc "How to write UCTRONICS SPI LCD3 5 Screen image to the SD card Windows The Raspberry Pi Beginners Guide")

# Q7: How to install the touchscreen driver and display driver for SPI LCD35 

A7:
- Step1: Expand the sd card first

> sudo raspi-config choose Advanced Operations -> Expand Filesystem
>  sudo reboot

- Step2: Update your raspberry pi system

> sudo apt-get update

- Step3: Download the driver package

> sudo git clone https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI.git

- Step4: Come in the UCTRONICS_LCD35_HDMI_RPI

> cd UCTRONICS_LCD35_RPI

- Step5: Get run permissions

> sudo chmod 777 UCTRONICS_LCD_backup

> sudo chmod 777 UCTRONICS_LCD35_install

> sudo chmod 777 UCTRONICS_LCD_restore

> sudo chmod 777 UCTRONICS_LCD_hdmi


- Step6: backup data

> sudo ./UCTRONICS_LCD_backup

- Step7: install our UCTRONICS LCD35 RPI driver

> sudo ./UCTRONICS_LCD35_install

wait a while the system will be installed and restarted automatically.

if you want to reuse the pre-installation system, you can use the below command

> sudo ./UCTRONICS_LCD_restore

If you want to display on hdmi instead of LCD,just use the below command

> sudo ./UCTRONICS_LCD_hdmi

# Q8: How to burn the UCTRONICS_LCD35_RPI.img?

> Step1: Download the burn tools from https://github.com/UCTRONICS/Win32DiskImager.git 

> Step2: Download the UCTRONICS_LCD35_RPI.img file from 

> http://uctronics.oss-us-west-1.aliyuncs.com/LCD35/image/UCTRONICS_LCD35_RPI.img 

> Step3: Open the SDFormatter to format your SD card 

> Step4: Open the Win32DiskImager to write the  UCTRONICS_LCD35_RPI.img to your SD card.

> For more details please refer to our video demo from https://www.youtube.com/watch?v=cCw91wH6mnc 





 
 
 
