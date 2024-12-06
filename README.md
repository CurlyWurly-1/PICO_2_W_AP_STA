# PICO_2_W_AP_STA
This PICO 2 W Micropython code presents a page in AP mode, then switches to STA mode.

Original code is from https://github.com/cpopp/MicroPythonSamples

This code has been adapted from https://github.com/tayfunulu/WiFiManager

 - Program "wifi_sta_ap.py" is to be executed only. Consider that program "wifimgr.py" is referenced as a library only in "wif_sta_ap.py" 
 - Upon execution of "wifi_sta_ap.py" the following happens
   - The webpage in "wifimgr.py" is presented in AP mode
   - The user populates the password for the selected SSID and presses enter
   - The program attempts to set up another server in STA mode and log into the SSID using the password
   - If logging into the SSID is successful
     - File "wifi.dat" is created which stores the login info 
     - The webpage "wifi_ap_sta.py" is presented in STA mode in the broadband network of the SSID
     - AP mode is exited

N.B. If the above sequence is completed successfully, the next time that "wifi_sta_ap.py" is executed, the login info in file "wifi.dat" is retrieved and a login is attempted. If the login is successful, the program bypasses AP mode and open only in STA mode i.e. the webpage in "wifi_sta_ap.py" is shown straight away. 
