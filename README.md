# PICO_2_W_AP_STA

The purpose of this program is to show how initial broadband SSID and password can be entered without hardcoding, via the use of functions in library "**wifimgr.py**" 

Original code is from https://github.com/cpopp/MicroPythonSamples

This code has been adapted from https://github.com/tayfunulu/WiFiManager

 - Program "**wifi_sta_ap.py**" is to be executed only.
 - Program "**wifimgr.py**" is only referenced as a library by "**wifi_sta_ap.py**". 
 - Upon execution of "**wifi_sta_ap.py**" the following process is seen and should be followed.
   - A HTML server in "**AP mode**" is setup and it presents the "login" HTML webpage as specified in "**wifimgr.py**" via a new SSID called "**WifiManager**".
   - Use your mobile phone to access SSID "**WifiManager**" with password "**123456789**".
   - Once your mobile phone is logged into SSID "**WifiManager**", use a browser on your phone to access the "login" HTML webpage via URL "**http://192.168.4.1**" 
   - In URL "**http://192.168.4.1**" , you will see a list of SSIDs that have been sniffed by the PICO W. Press the radio button next to the SSID you want to access, populate the password field with the correct password and press SUBMIT.
   - The program takes the login info you have entered, _and attempts to log into the selected SSID and set up another server in **STA mode**_ 
   - If logging into the selected SSID is successful.
     - File "**wifi.dat**" is created and the login info is stored in JSON format.
     - The HTML webpage as specified in "**wifi_ap_sta.py**" is presented in **STA mode** and it can be accessed as a new IP address in the broadband network of the SSID (e.g. _"http://192.168.x.yyy"_ ).
     - AP mode is exited and this means that SSID "**WifiManager**" will disappear. Redirect your mobile phone to use the broadband network of the SSID and use a browser to access the new IP address (e.g. _"http://192.168.x.yyy"_ ). This IP address will display the HTML webpage as specified in "**wifi_ap_sta.py**"
     - Hard reboot the PICO W as follows
       - Disconnect the PICO W USB connection.
       - Connect the PICO W USB connection
       - Press the "Stop" button in Thonny (to reconnect Thonny to the PICO W)
       - Execute program "**wifi_sta_ap.py**" again    

N.B. If the above sequence is completed successfully, with the PICO W hard rebooted amd program "**wifi_sta_ap.py**" has been executed again, you will notice that because the program now finds file "**wifi.dat**" with its login info, the program will bypass the "setup" HTML webpage in **AP mode** and the HTML webpage in "**wifi_sta_ap.py**" is shown straight away. IF however, the file contains the wrong SSID and password combination (perhaps the SSID password has changed?) then after two unsuccessful attempts to login in **STA mode**. the program will go back to showing the original "login" HTML webpage in **AP mode**.  
