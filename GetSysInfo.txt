#!/bin/bash
# Antoinette's Bash Scripting Project for CIS 272 
echo "output file is : Get_Sys_Data"

echo "Gather System Information" > Get_Sys_Data 
echo >> Get_Sys_Data 

# get the System Hostname 
echo "The system hostname is: " >> Get_Sys_Data 
hostname >> Get_Sys_Data
echo >> Get_Sys_Data 

# get the Operating System 
echo "The Operating System is:" >> Get_Sys_Data 
uname -o >> Get_Sys_Data 
#cat /etc/os-release    #alternate method
echo >> Get_Sys_Data 

# get system uptime 
echo "The system has been online since:" >> Get_Sys_Data
uptime >> Get_Sys_Data 
echo >> Get_Sys_Data 

# get the Linux Kernel version 
echo "The Linux Kernel version is:" >> Get_Sys_Data  
uname -v >> Get_Sys_Data 
echo >> Get_Sys_Data 
#lsb_release -a >> Get_Sys_Data 
echo >> Get_Sys_Data 
echo >> Get_Sys_Data

# get CPU information 
echo "Basic CPU information:" >> Get_Sys_Data 
uname -p >> Get_Sys_Data 
echo >> Get_Sys_Data
echo "Machine Information" >> Get_Sys_Data
uname -i >> Get_Sys_Data
hostnamectl >> Get_Sys_Data
 
echo >> Get_Sys_Data

# pause output and wait for user 
#echo "press <Enter> to continue   #use this line to display on a screen
#read continue   #use this line to display on a screen 

echo >> Get_Sys_Data 

# get IP information 
echo "IP information:" >> Get_Sys_Data 
ip addr show >> Get_Sys_Data 

echo >> Get_Sys_Data 
echo >> Get_Sys_Data 

# Get memory information 
echo "Memory data:" >> Get_Sys_Data 
free -h >> Get_Sys_Data 
echo >> Get_Sys_Data 
echo >> Get_Sys_Data 

# pause output and wait for user 
#echo "press <Enter> to continue   #use this line to display on a screen
#read continue   #use this line to display on a screen 

#Get file system statistics
echo "File System usage" >> Get_Sys_Data
df -h >> Get_Sys_Data
echo >> Get_Sys_Data
echo >> Get_Sys_Data

# pause output and wait for user 
#echo "press <Enter> to continue   #use this line to display on a screen
#read continue   #use this line to display on a screen 

#journalctl -n 5 -g "error"      #for systems where /var/log/syslog is not available (kali) 

#Get the last 5 system error logs
echo "These are the last 5 system error logs:" >> Get_Sys_Data
grep "error" /var/log/syslog | tail -n 5 >> Get_Sys_Data
echo >> Get_Sys_Data
echo "End of File" >> Get_Sys_Data
echo "System Information saved to file."