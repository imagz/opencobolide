### 1. Search the Terminal app in Finder
- Open Finder
- Select the Application tab
- Open macOS default 'Utilities' folder 

or

- Click on 'Go' on the menu bar
- Select Utilities

### 2. Select the 'Terminal' app
<br> 

### 3. Secondary Click on the 'Terminal' app.
<br>

Depending on how you have the Secondary Click
setup you might have 'Click with two fingers' or 'Right Click' option selected on the mouse settings or if you are using a trackpad 'Click with two fingers', 'Click in bottom right corner' or 'Click in bottom left corner' option selected. If you haven't set any of that by default the option to click with two fingers is selected to get more settings within a file.<br>

### 4. Select Get Info
<br>

### 5. After the 'Terminal Info' window has open select the check box 'Open using Rosetta'

<p>Rosetta enable Macs with Apple Silicon processor to use programs made for Macs with Intel processor.
<p>If you skip this steps OpenCobolIDE will not detect automatically cobol compiler and if you want the latest version of OpenCobolIDE (4.7.6) you will have problem installing it and its dependecies.
<p>The reason that it does not detect the compiler is because when homebrew is install without having Rosetta enable on 'Terminal' it will be install on another directory `opt/bin/homebrew`, which the compiler will also be, instead of 'usr/local/bin' which OpenCobolIDE is set by default to detect.
<p>If you are an advanced user you might have an idea on how to have installed and use two versions of homebrew if you have a lot of homebrew programs installed for other things which uninstalling could break and uninstall other programs or there is a specific reason two have both but if you are not an advanced user is better to uninstall homebrew and any other program that you might have installed with homebrew and install it again with Rosetta enable on 'Terminal' to prevent any issues.

### 6. Close 'Terminal Info' window.
<br>

<p>NOTE: If you had Terminal open while enabling Rosetta on Terminal make sure to close the app so when is open again it will be open with Rosetta.
<br>

### 7. Open 'Terminal' app

<br>

### 8. After 'Terminal' loads copy the next command, paste it on Terminal and hit enter to install homebrew.

<br>

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

<br>

### 9. It will prompt you to enter the computer password.

<br>

### 10. After some progress if you don't have installed the Command Line Tools for Xcode it will prompt you to install it and will probably prompt you to input your computer password again.
<br>

### 11. If homebrew installation is successful and Terminal directed you to the user directory we can move to the next part.
<br>

### 12. Install GNU-COBOL by copying the next command, pasting it on Terminal and hitting enter.
<br>

`brew install gnu-cobol`

<br>

### 13. If GNU-COBOL installation doesn't present any errors and Terminal directed you to the user directory we can move to the next part.
<br>

### 14. Then install Python 3.9.6 by copying the next command, pasting it on Terminal and hitting enter.
<br>

`brew install python@3.9`

<br>
<p>The reason that is recommended to uninstall any version of Python installed in the computer is because in order to OpenCobolIDE work it needs to have specifically Python version 3.9.6 installed. If you don't specify the version of Python to be installed on homebrew it will install Python 3.10 which is not compatible with OpenCobolIDE because they took out and change things that OpenCobolIDE needs to work.

## **The next series of steps only applies to Macs with Apple Silicon Processors (M1/M2)**
<br>

### 15. Install 'Python Virtual Enviroments' by copying and pasting the next command to 'Terminal' and hitting enter.
<br>

`sudo pip3 install virtualenv`

<br>
<p>Make sure to leave 'sudo' before the command because the next command will not work if is installed without 'sudo' and it will need to be uninstalled and installed again.

### 16. Input the next command on 'Terminal' and hitting enter.
<br>

`virtualenv venv`

<br>

### 17. Then input the next command on 'Terminal and hit enter. 
<br>

`source venv/bin/activate`

<br>
This create a new directory in the user folder which will contain OpenCobolIDE and its dependencies. For some reason if is not installed like this on Macs with Apple Silicon Processor the installation of OpenCobolIDE will not work.
<br>

### 18. Install PyQt5 by entering the next command on "Terminal'
<br>

`pip install PyQt5`

<br>
<p>While there is a recent version of PyQt (PyQt6) and it works without Rosetta it is not compatible with OpenCobelIDE.
<br>

### 19. Finally! after some commands is now time to install OpenCobolIDE by entering the next command on 'Terminal'.
<br>

`pip install OpenCobolIDE`

<br>

### 20. To check if the installation of OpenCobolIDE and of all its dependencies went perfect enter the next command in the Terminal or copy and paste it in the Terminal and then hit enter.
<br>

`OpenCobolIDE` 

<br>
<p>If OpenCobolIDE opened then the installation went flawless. Now lets check if Cobol compiler works.

### 17. Go to 'Preferences'. 
<br>

<br>

### 18. Select the 'Compiler' tab if is not selected.
<br>

<br>

### 19. Click on 'Check compiler'.
<br>

<br>

### 20. After the small window opens press 'Check compilation'.
<br>

<br>

<p>If on the 'Output' view it says 'Compiler works!' it means it recognized the cobol compiler and it works Congratulations!.
<br>

<br>

### 21. To have a shortcut to open OpenCobolIDE without entering 'OpenCobolIDE' command on Terminal search 'opencobolide' in 'Finder' or search this directory `/Users/YOUR_USERNAME/venv/bin/opencobolide` and copy the executable file and paste it on whatever place you like it to be.

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"

### 12. If Python 3.9.6 installation doesn't present any errors, is installed successfully and Terminal directed you to the user directory we can move to the next part.
