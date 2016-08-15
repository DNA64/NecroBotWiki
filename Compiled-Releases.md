## Compiled Releases

# Getting Started - Compiled Release Setup

Note: You will need some basic Computer Experience. Need help? Join the [Chat!](https://github.com/DNA64/NecroBotWiki/blob/master/Chat-%26-Rules.md#chatting-using-discord) The Issue Tracker is not for help!

## Installation & Configuration

### Compiled release steps are recommended for any end-user who has no intention of modifying the source code.

### Using compiled release

1.  Download the latest official release (0.8.6) Release.zip using Google Search etc.
2.  Unzip the downloaded files, run the program (NecroBot.exe).
3.  A console window will appear and then soon close. This is generating the config/auth JSON files.
4.  Navigate to the Config/auth.json file.
5.  Change AuthType to `google` or `ptc` based on your login type of choice.
6.  Enter your username and password with quotes around them. You can find an example below.
  * For Google logins, use `GoogleUsername` and `GooglePassword`.
If the Google login uses 2-factor authentication, you will be prompted when Necrobot attempts to login.
  * For PTC logins, use `PTCUsername` and `PTCPassword`. Make sure to keep the quotations " " in front and at the end.
  
```  
For Google   
 auth.json   
{   
   "AuthType": "google",   
   "GoogleUsername": "youremail@gmail.com",   
   "GooglePassword": "yourgooglepassword",   
   "GoogleRefreshToken": null,   
   "PtcUsername": null,   
   "PtcPassword": null   
 }
``` 

``` 
For PTC
 auth.json
 {
   "AuthType": "ptc",
   "GoogleUsername": null,
   "GooglePassword": null,
   "GoogleRefreshToken": null,
   "PtcUsername": "yourptcusername",
   "PtcPassword": "yourptcpassword"
 }
 ```
 
1.  Save the `auth.json` file.
2.  Edit `Config/config.json` with your desired settings.
  * The defaults settings are generic so you WILL have to modify these to match what you desire from NecroBot.
  * More details on these settings can be found here (#config)
  * For GPX Path Setup, follow the guide at GPX Pathing Setup (#gpx-pathing-setup)
  * For Sniping Setup, follow the guide at Sniping Setup
3.  Insert your latitude and longitude values in the `DefaultLatitude` and `DefaultLongitude` variables.
  * You can find GPS coordinates [here](http://mondeca.com/index.php/en/any-place-en) to fit your desired location.
4.  Save the `config.json` file.
5.  Run `NecroBot` again.
  * If you are using a Google account to login which is setup with 2-factor authentication, NecroBot will open a Google page in your default browswer and request for your 2-factor token.
6. Enjoy!

## Changing the Location of the Bot

1.  If your Bot is running, close it.
2.  Change the value of `DefaultLatitude` and `DefaultLongitude` in your `Config/config.json` file.
3.  Run the bot. Done!
