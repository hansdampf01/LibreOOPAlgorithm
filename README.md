# LibreOOPAlgorithm


## How to build for us sensors (and maybe even germany and other countries).
Currently only the version below of xDrip works with the new OOP, and only with manual scanning.
Once I'll know that this works, I'll continue to work with hw vendors to have full support.

### building the apk
git clone https://github.com/tzachi-dar/LibreOOPAlgorithm.git<br/>
cd LibreOOPAlgorithm<br/>
git checkout libre-us-new-sensor<br/>
scripts\create_apk.cmd<br/>

Install the apk: adb install -r LibreOOPAlgorithm.apk<br/>
Open the apk, and make sure that you see the message "Algorithm worked correctly".<br/>


### Download and install xdrip on your phone
(if you already have xdrip on your phone, you will have to remove it first. You can backup your DB and settings first).  
1) You must use the version from here: https://drive.google.com/file/d/1I7oZw9KRnclsY2MoZgeiRNKNtKv2W44M/view?usp=sharing
1) Choose libre as the sensor type.
1) Choose miaomiao
1) Go to settings->hw data source and choose libre wifi
1) Go to list of receivers and enter 127.0.0.1:5000
1) Go to nfc scan features-> enable scanning
1) Start a new sensor (answer not today).
1) Go to settings->less common settings->other misc options-> and set "use oop algorithm"  
Now use xdrip to scan the libre.  
Hopefully all will work. Let me know in any case.  






## Normal oop 




This is an apk that allows translating libre sensor readings to blood glucose.
It has been able to get results extremely close to the libre reader without any calibrations.
Should be used with xDrip-plus.

## TLDR: To create the apk, please do the following (on a windows pc):

Make sure that your pc has android studio instaled. follow the movie at https://developer.android.com/studio/install.html for instructions on how to install android studio. <br/>

Creating the apk using chrome:

1) You are now on the page: https://github.com/tzachi-dar/LibreOOPAlgorithm.
2) Press clone or download. Then Download zip.
3) On the downloaded file, right click "show in folder".
4) right click "Extract all ...". Press extract.
5) A new windows will be opened, double click LibreOOPAlgorithm-master
6) double click windows_create_apk.cmd (If windows will ask for permission to run the file, please allow it).
After a few seconds the file LibreOOPAlgorithm.apk will be in the directory.
Send it by mail to the phone and install it.

Here is a short youtube video showing what you should do: https://www.youtube.com/watch?v=PfLHT9pI058&
(If this is taking more then 60 seconds, you need to practice.)

On your phone, Open the apk. If you see a message saying "The algorithm worked successfully" all is done. If you see an error message please let me know. <br/>

from command line (advanced) run

The apk that you need to install is LibreOOPAlgorithm.apk
Before doing it, please go to settings->security and turn on "unknown sources"

You can install the apk in anyway you like, for example: adb install LibreOOPAlgorithm.apk
git clone https://github.com/tzachi-dar/LibreOOPAlgorithm.git<br/>
cd LibreOOPAlgorithm<br/>
scripts\create_apk.cmd<br/>


You can also send it by mail (or copy) it to your phone and install it from there.<br/>


# If you are using Mac or linux, please do the following:
Download and install java jdk first to make sure the "jarsigner" command is available !


git clone https://github.com/tzachi-dar/LibreOOPAlgorithm.git

cd LibreOOPAlgorithm

./scripts/download_apk.sh

./scripts/create_apk.sh

## Setting xDrip to work with the oop Algorithm.

Currently Tomato (MiaoMiao), BluCon, LibreAlarm and direct scanning supports the Libre OOP Algorithm. <br/>

xDrip has to be at a version after  21st may 2018 nightly. (This probably means that you have to download the latest nightly).

On xdrip go to setting->less common settings->other misc options-> and set out of process blukon algorithm. 
(If this option is disabled, this means that your version of xDrip is too old).

## The propose of this project is to allow opensource projects to use the same algorithm for bg calculation.
This is a specific example that simulates official results, but anyone can implement whatever algorithm that he wants.

Please see the class IntentsReceiver for how to send and receive intents with raw data from the libre sensor.
