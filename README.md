# How to Install OpenCobolIDE (4.7.6) on macOS latest version
<br>

NOTE: If you tried to install OpenCobolIDE or the Cobol compiler with Homebrew or have Homebrew or Python installed in your computer it is recommended to uninstall both to prevent any issues unless you are an advanced user and know how to have two versions of Homebrew or multiple version of Python. Also before uninstalling Homebrew and Python I recommend uninstalling any program that are OpenCobolIDE dependecies because depending on the command used to install the programs it can cause issues and some programs stay installed somehow even if Python and Homebrew is uninstalled. I recommend uninstalling the following programs in the order listed.

<br>

Command to uninstall OpenCobolIDE: `pip3 uninstall OpenCobolIDE`

<br>

Command to uninstall PyQt5: `pip3 uninstall PyQt5`

<br>

Command to uninstall Python Virtual Enviroment: `pip3 uninstall virtualenv`

<br>

Command to uninstall Python: `brew uninstall python3`

<br>

Command to uninstall Cobol Compiler: `brew uninstall gnu-cobol`

<br>

Command to uninstall Homebrew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"` 

<br>

### 1. Search the Terminal app in Finder.
- Open 'Finder' app.
- Select the 'Application' tab.
- Open macOS default 'Utilities' folder.

or
- Click on 'Go' on the menu bar.
- Select Utilities.

<br>

### 2. Select the 'Terminal' app.
<br> 

### 3. Secondary Click on the 'Terminal' app.
<br>
Depending on how you have the Secondary Click settings setup, if you even have it set it up at all, it might be use in a different way. If 'Right Click' option is selected on the mouse settings you need to right click or if you are using a trackpad and have 'Click in bottom right corner' or 'Click in bottom left corner' option selected you need to press the trackpad in the place it says in the option that is selected to Secondary Click. If you have not set any of that by default the option of 'Click with two fingers' is selected that means you need to click with two fingers at the same time to Secondary Click.<br>

<br>

### 4. Select 'Get Info'.
<br>

### 5. After the 'Terminal Info' window has open enable the check box 'Open using Rosetta'
<br>
<p>Rosetta enable Macs with Apple Silicon processor to use programs made for Macs with Intel processor.

If you skip this steps OpenCobolIDE will not detect automatically cobol compiler and if you want the latest version of OpenCobolIDE (4.7.6) you will have problem installing it and its dependecies.

The reason that it does not detect the compiler is because when homebrew is install without having Rosetta enable on Terminal it will be install on another directory `opt/bin/homebrew`, which the compiler will also be, instead of `usr/local/bin` which OpenCobolIDE is set by default to detect.

If you are an advanced user you might have an idea on how to have installed and use two versions of homebrew if you have a lot of homebrew programs installed for other things, which uninstalling could break or uninstall other programs, or there is a specific reason two have both but if you are not an advanced user is better to uninstall homebrew and any other program that you might have installed with homebrew and install it again with Rosetta enable on Terminal to prevent any issues.
<br>
  
<br>

### 6. Close 'Terminal Info' window.
<br>

NOTE: If you had Terminal open while enabling Rosetta on Terminal make sure to quit the app so when is open again it will open with Rosetta.

<br>

### 7. Open 'Terminal' app
<br>

NOTE: Make sure you open Terminal with Rosetta or you will have a bad day if you continue the rest of the steps. To make sure you have open Terminal with Rosetta input this command `arch` on Terminal and hit enter, if the output is: `i386` you are good to go. Now if the output is `arm64` make sure you made the previous steps correctly, quit Terminal, open it and check again.

<br>

### 8. After 'Terminal' loads copy the following command, paste it on Terminal and hit enter to install homebrew.

<br>

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

<br>

### 9. It will prompt you to enter the computer password.

<br>

### 10. After some progress if you don't have installed the Command Line Tools for Xcode it will prompt you to install it and will probably prompt you to input your computer password again.
<br>

### 11. If homebrew installation is successful and Terminal directed you to the user directory we can move to the next part.
<br>

### 12. Install GNU-COBOL by copying the following command, pasting it on Terminal and hitting enter.
<br>

`brew install gnu-cobol`

<br>

### 13. If GNU-COBOL installation doesn't present any errors and Terminal directed you to the user directory we can move to the next part.
<br>

### 14. Then install Python 3.9.6 by inputting the following command on Terminal and hitting enter.
<br>

`brew install python@3.9`

<br>
<p>The reason that is recommended to uninstall any version of Python installed in the computer is because in order to OpenCobolIDE work it needs to have specifically Python version 3.9.6 installed. If you don't specify the version of Python to be installed on homebrew it will install Python 3.10 which is not compatible with OpenCobolIDE because they took out and change things that OpenCobolIDE needs to work.
<br>

<br>

## **The next series of steps only applies to Macs with Apple Silicon Processors (M1/M2) if you are trying this on a Mac without an Apple Silicon Processor skip to step 18.**
<br>

### 15. Install 'Python Virtual Enviroments' by copying and pasting the next command to 'Terminal' then hit enter.
<br>

`sudo pip3 install virtualenv`

<br>
NOTE: Make sure to leave 'sudo' before the command because the next command will not work if is installed without 'sudo' and it will need to be uninstalled and installed again.
<br>

<br>

### 16. Input the next command on Terminal and hit enter.
<br>

`virtualenv venv`

<br>

### 17. Then input the following command on Terminal and hit enter. 
<br>

`source venv/bin/activate`

<br>
This create a new directory in the user folder which will contain OpenCobolIDE and its dependencies. For some reason if is not installed like this on Macs with Apple Silicon Processor the installation of OpenCobolIDE will not work.
<br>

<br>

### 18. Install PyQt5 by entering the next command on Terminal.
<br>

Macs with Apple Silicon Processors (M1/M2): `pip install PyQt5`

Macs with other processors: `pip3 install PyQt5`

<br>
<p>While there is a recent version of PyQt (PyQt6) and it works without Rosetta it is not compatible with OpenCobelIDE.
<br>

<br>

### 19. Finally! after some commands is now time to install OpenCobolIDE by entering the next command on 'Terminal'.
<br>

Macs with Apple Silicon Processors (M1/M2): `pip install OpenCobolIDE`

Macs with other processors: `pip3 install OpenCobolIDE`
<br>

<br>

### 20. To check if the installation of OpenCobolIDE and of all its dependencies went perfect enter the next command in the Terminal or copy and paste it in the Terminal and then hit enter.
<br>

`OpenCobolIDE` 

<br>
<p>If OpenCobolIDE opened then the installation went flawless. Now lets check if Cobol compiler works.
<br>

<br>

### 21. Go to 'Preferences'. 
<br>

<br>

### 22. Select the 'Compiler' tab if is not selected.
<br>

<br>

### 23. Click on 'Check compiler'.
<br>

<br>

### 24. After the small window opens press 'Check compilation'.
<br>

<br>

<p>If on the 'Output' view it says 'Compiler works!' it means it recognized the cobol compiler and it works.
<br>

<br>

### 25. To have a shortcut to open OpenCobolIDE without entering `OpenCobolIDE` command on Terminal search 'opencobolide' in 'Finder' or search this directory `/Users/YOUR_USERNAME/venv/bin/opencobolide` and copy the executable file and paste it on whatever place you like it to be.
