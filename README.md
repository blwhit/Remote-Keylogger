# Remote-Keylogger

## Project Goal:
Create a remote keylogger in python, disguise as photo, remote transmit, create a fun saftey key to stop program. 


# Code 

### Imports
Begin with imports from python libraries that will make the code possible:



- tkinter: for creating a GUI popup on screen
- pynput.keyboard: for capturing keystrokes
- logging: for creating logfiles
- os: for itneracting with the host OS (Windows)
- getpass/uuid/socket: get host information
- threading: executing procceses in unique threads
- subprocess: running system commands


![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/9e115aff-8e2e-409b-9bbf-d62d3bc851ee)




### Setup
This section of code configures the SMTP email service to use, along with the temporary file to write all of the logs to. The temporary file created is disguised to blend in with Windows files as "license_win64_details.txt". Using Gmail's SMTP service, I will be able to send emails to remotely extract the information.
![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/0a022bfe-87fb-42ea-8a74-d7c0045651b1)





### Host Info, Wifi Profiles
These functions will run once at the beginning of execution, and will collect host information about the machine its running on including: hostname, IP, username, saved wifi profiles, MAC address, and username.


![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/6747a5ba-1e51-43d8-bff7-5e829d83d227)



### Main Loop
Here are the main functions and main loop of the code. The program will begin listening for keystrokes and writing them to a temp file that will automatically send the data incrementally when the filesize reaches 500 bytes (and on program termination). The program works by creating threads for listening and execution, infinitely logging all keystrokes, writing them to a file, and emailing the file. By default there is a safety key which terminates the program, the right control button. Hitting the exit key will stop the program, delete the temp files, and flash a popup as a fun easter egg.


![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/c29d6a39-80ca-4572-9425-0ac773a30c5c)


![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/2548d15d-8991-4fa3-9cb6-a50de1675936)




# Executable compile
The python program can be compiled into a standalone executable through the commandline using PyInstaller. If we save the python file as a ".pyw" extension, the program will run in a mode "without console", meaning that it will run without popping up command prompts or new windows. This will help to stay undetected.


![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/5d7653d1-0b7f-4886-aa40-49a9b0169b5c)




# WinRAR packaging 
Using WinRAR we can package the files to be an SFX archive. The program will now be embedded into a photo, and when the photo is opened it will execute the keylogger under the radar. We can disguise the icon and the opening of the file, but cannot get the file type to change from "Application".

![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/46876b89-509c-427f-860e-f204f4142bd0)

![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/bc63538d-7f93-4f38-8f5f-d87b07617466)


# Demo
After opening the photo, the executable will run and begin sending emails of the host information and keystrokes. This will loop until the user presses the right ctrl key and terminates the program. 

![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/096169bd-d7d6-4962-8627-5472c7343a40)

![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/20157876-6d44-429e-88f4-2b1fa07c4baf)

![image](https://github.com/blwhit/Remote-Keylogger/assets/141170960/0eb89d96-fde9-45c1-8175-40b651295a86)






