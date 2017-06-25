# UCTRONICS_LCD35_RPI

This driver package is used for UCTRONICS 3.5 inches LCD which can run on Raspbery Pi zero Pi2 Pi3 Model B/B+ paltforms.

In order to use it easier,we provide you operation steps in detail. 

Step1: Expand the sd card first

 > sudo raspi-config choose Advanced Operations -> Expand Filesystem 
 
 > sudo reboot
  
Step2: Update your raspberry pi system

 >  sudo apt-get update

Step3: Download the driver package

  > sudo git clone https://github.com/UCTRONICS/UCTRONICS_LCD35_RPI.git
  
Step4: Come in the UCTRONICS_LCD35_RPI

  > cd UCTRONICS_LCD35_RPI
  
Step5: Get run permissions

 > sudo chmod 777 UCTRONICS_LCD_backup
 
 > sudo chmod 777 UCTRONICS_LCD35_install
 
 > sudo chmod 777 UCTRONICS_LCD_restore
 
 > sudo chmod 777 UCTRONICS_LCD_hdmi
 
Step6: backup data

 > sudo ./UCTRONICS_LCD_backup
 
Step7: install the LCD35 driver

 > sudo ./UCTRONICS_LCD35_install
 
wait a while the system will be installed and restarted automatically.

if you want to reuse the pre-installation system, you can use the below command

 > sudo ./UCTRONICS_LCD_restore
 
 If you want to display on hdmi instead of LCD,just use the below command
 
  > sudo ./UCTRONICS_LCD_hdmi
 
 



