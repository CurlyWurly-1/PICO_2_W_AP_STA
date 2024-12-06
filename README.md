# PICO_2_W_AP_STA

The purpose of this program is to show how initial broadband SSID and password can be entered without hardcoding, via the use of functions in library "**wifimgr.py**" 

Original code is from https://github.com/cpopp/MicroPythonSamples

This code has been adapted from https://github.com/tayfunulu/WiFiManager

 - Program "**wifi_sta_ap.py**" is to be executed only.
 - Program "**wifimgr.py**" is only referenced as a library by "**wifi_sta_ap.py**". 
 - Upon execution of "**wifi_sta_ap.py**" the following process is seen and should be followed.
   - The HTML webpage as specified in "**wifimgr.py**" is presented in **AP mode** and it can be accessed via a new SSID called "**WifiManager**" with a password of "**123456789**".
   - When you have loged into the SSID called "**WifiManager**", access URL "**http://192.168.4.1**" 
   - In URL "**http://192.168.4.1**" , select the SSID, populate the password field and press SUBMIT.
   - The program takes the login info you have entered, and attempts to set up another server in STA mode to log into the selected SSID.
   - If logging into the selected SSID is successful.
     - File "**wifi.dat**" is created and the login info is stored in JSON format.
     - The HTML webpage as specified in "**wifi_ap_sta.py**" is presented in **STA mode** and it can be accessed as a new IP address in the broadband network of the SSID. 
     - AP mode is exited.

N.B. If the above sequence is completed successfully, the next time that "**wifi_sta_ap.py**" is executed, the login info in file "**wifi.dat**" is retrieved and a login is attempted. If the login is successful, the program bypasses AP mode and open only in STA mode _i.e. If there is correct log in info in the "**wifi.dat**" file, the webpage in "**wifi_sta_ap.py**" is shown straight away_. 
