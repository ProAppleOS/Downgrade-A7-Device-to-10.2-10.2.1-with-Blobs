Copyright by iloveapple1999 © ;
MADE BY @iloveapple1999 on Twitter; 
ANY QUESTION? -> @iloveapple1999 on Twitter 

# Downgrade-A7-Device-to-10.2-10.2.1-with-Blobs
How to Downgrade A7 Device from 10.3.x to 10.2/10.2.1 with Blobs

DOING THIS IS AT YOUR OWN RISK! I'M NOT RESPONSIBLE FOR ANYTHING. I´M NOT RESPONSIBLE IF SOMETHING BREAKS! I´M NOT PAYING FOR A NEW DEVICE IF SOMETHING BREAKS ON YOUR DEVICE! AGAIN! DOING THIS IS AT YOUR OWN RISK!

Requirements:
a Mac (or virtual Machine)  , A7 device on 10.3.x , SHSH Blobs for 10.2 or 10.2.1 , your iDevice on 10.3.x

1. Plug your device into Mac. Open iTunes, click on your device. 
2. Click on your serial Number 3 Times.
3. Then you see your iPhones Model identifier.
4. If your Model identifier is one of these down you can use this Method to downgrade:
   iPad4,1 iPad4,2 iPad4,3 iPad4,4 iPad4,4 iPad4,6
   iPhone6,1 iPhone6,2
   
If your model identifier is listed there you can be happy because now you can downgrade to 10.2/10.2.1 with Blobs :)

*
Currently Supported Devices for DOWNGRADING is just the iPhone 5s, if you want to Downgrade your iPad, you need to find       Offsets and put it in Xcode Project and Compile it! How to find Offsets for v0rtex ( https://gist.github.com/uroboro/5b2b2b2aa1793132c4e91826ce844957 ) Video Tutorial ( https://www.reddit.com/r/jailbreak/comments/7iyyfh/tutorial_finding_offsets_for_v0rtex/?st=JB8AZGLS&sh=7780eff2 )
*

                                                 DOWNLOADS:

1. Download iPSW for your Device! You need iOS 10.3.3 IPSW for SEP and baseband and 10.2 IPSW or 10.2.1 IPSW. This depends on which Version you want to restore to. At the end you need 2 IPSW. You can Download iPSW here: www.ipsw.me 
2. Download & install Xcode (Xcode from MacAppStore).
3. Download v0rtexNonce. ( https://github.com/arx8x/v0rtexNonce )
4. Download Custom Buildmanifest here (Download that file with your Model identifier you looked up before on iTunes ) ( https://www.dropbox.com/sh/edrpjiek184trc9/AADxrcE2Bz2CGRgbMG9kxub8a?dl=0&lst= )
5. Download latest Version from futurerestore ( http://api.tihmstar.net/builds/futurerestore/futurerestore-latest.zip )

                                                 Lets Go :)

1. Unzip v0rtexNonce
2. Open unzipped folder
3. Double click on v0rtexNonce.xcodeproj
4. Click Open
5. Go to Xcode -> Preferences -> Accounts -> click + -> Sign in with your AppleID (no developer account needed)
6. Close Accounts Window
7. Click on the left top at the blue file named v0rtexNonce
8. Change the „Bundle Identifier" to something you want like for example „downgrade.mydevice"
9. Click at the middle on „Unknown Name" and select your AppleID. There is (Personal Team)
10. Wait until the Red text is gone
11. Plug in your device and select at the top next to STOP button your Device.
12. Click on Play Button.
13. Unlock your device.
14. Ignore the popup in Xcode saying „Could not launch v0rtexNonce"
15. Open Settings on your iPhone. Go to General -> Profile & Device Managment -> Click on your Apple ID -> Click on Trust -> Trust again.
16. Now Open v0rtexNonce. If your Device isn´t supported or your Offsets are wrong the App will Crash.
17. If there is „Exploit failed" Reboot and Try again until you get a Nonce in App looks like this ( 0x23ae4a983ds7 )

                                     Now you got your Nonce. Great Lets go further :D
                                     
                                     
1. Create a folder on Desktop name it „Downgrade"
2. Put the iOS 10.2 IPSW into the „Downgrade" folder.
3. Put the Custom Buildmanifest file you downloaded first into „Downgrade" folder.
4. Open futurerestore folder and put the file futurerestore_macos into the „Downgrade" folder.
4. Change the iOS 10.3.3 IPSW name at the end to .zip
5. Unzip iOS 10.3.3 iPSW (take some seconds)
6. Open folder
7. Get the Baseband file (on iPhone 5s it is Mav7Mav8... .bbfw)
8. Put the Baseband file into „Downgrade" folder
9. Install App „Battery Memory System Status Monitor" open app and go to System and look for Model number ( https://goo.gl/vWJBy4 ) 
9. Open the folder „all_flash"
10. look for „sep-firmware.(Model number).release.im4p" IMPORTANT take the one .im4p NOT the .im4p.plist
         for example   sep-firmware.n51.release.im4p
11. Put that file into „Downgrade" folder
12. Copy your SHSH2 blob from iOS 10.2 / iOS 10.2.1 and put into „Downgrade" folder.
13. Rename your Blob name to „blob.plist"        NOT „blob.shsh2.plist" !
14. Click „use .plist"
15. Open your SHSH Blob.
16. Go to bottom and some of you see Generator „<String>0x23ae4a983ds7<String>" or just generator String „0x23ae4a983ds7"
17. Change the „0x23ae4a983ds7" to the Nonce that you got in the v0rtexNonce App! This means put the 0x...... Nonce that you got in the v0rtexNonce app on your phone into <String>0x......<String> or change the 0x....
18. Don´t change amything else!
19. Close the file.
20. Rename your blob to „blob.shsh2" NOT „blob.shsh2.plist" or NOT „blob.plist.shsh2"
21. Click "use .shsh2"

Now you are all set for your Downgrade! Now you should have this in the „Downgrade" folder on Desktop:
Buildmanifest.plist
Mav7Mav8... .bbfw
blob.shsh2
futurerestore_macos
sep-firmware.(Model number).release.im4p    for example sep-firmware.n51.release.im4p
iOS 10.2 IPSW

                              NOW THE DOWNGRADE PROCESS! Be patient! Don´t type anything wrong!
                              
1. Open Terminal
2. write chmod 775 (drag futurerestore_macos file from your Downgrade folder into Terminal) and click enter
3. write cd (drag your Downgrade folder into Terminal) and enter
3. type ls and enter
4. now you should see all the files in your Downgrade folder
5. drag futurerstore_macos file into terminal and click enter (you should see lots of commands)
6. write this ./futurerestore_macos -t (drag blob) -b (drag Mav7) -p (custom BuildManifest) -s (drag sep) -m (custom buildmanifest) (iphone10.2.ipsw)
7. for an example look here ( https://imgur.com/a/wUzZH )
8. Plug your Device in
9. Unlock your Device
10. CROSS FINGERS AND click Enter in Terminal
11. ITS NORMAL THAT YOUR DEVICE TURNS INTO GREEN!
11. Now it should work 
12. Wait about 5-10 Minutes
13. at the end it should look like this ( https://imgur.com/a/9Tl6s )
14. Your Phone now Restart.
15. Set up your Device
16. Install Yalu or Saigon
17. Jailbreak :D

                                             DONE! ENJOY YOUR JAILBREAK :D
                                             
THANKS TO @tihmstar
THANKS TO @siguza
THANKS TO @arx8x
                                             
                                           MADE BY @iloveapple1999 on Twitter 
   






   

