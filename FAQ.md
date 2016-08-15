## FAQ overview

  * Why is NecroBot requesting an email and password instead of Google OAuth token
  * Every Pokemon I try to catch returns CatchFlee and I cannot claim any Pokestops
  * How do I run NecroBot without any prompts?
  * Can I still login to my account on the Pokemon GO app while NecroBot is running?
  * When I try to build the source code, I receive "One or more projects were not loaded correctly"
  * How do I run multiple bots at once?
  * When I launch the .exe after setting my configurations, the app immediately crashes and displays a bunch of JSON reference exceptions
  * How do launch the Google login process again to change accounts?
  * After I paste my device code into google.com/device, Necro-Bot logs into the wrong account. How do I log into the right account?
  * How often does the bot evolve Pokemon, recycle items, or rename Pokemon?
  * How does egg hatching work?
  * How do I use Lucky Eggs before the bot evolves Pokemon?
  * How can I use incense, lucky eggs, and incubators?
  * How do I ignore to catch a Pokemon?
  * Why is my bot recycling items?
  * Why are some Pokemon not being transferred?
  * Why do I receive the "(ATTENTION) PokemonInventory is Full. Transferring pokemons..." error over and over?
  * Why do I receive the "(ATTENTION) Encounter problem: Lure Pokemon NotAvailable" error?
  * I have so many candies for one Pokemon and I want to use them for experience farming. How do I do that?
  * Why are PokeStops not being loaded in the console?
  * My Bot is repeating DisplayHighestCP
  * Why is this Bot a bit slower than others?
  * What does IV mean?
  * Where can I find the change location?
  * How do I know which radius value to use?
  * How do I configure the bot to not catch any Pokemon?
  * I received a "An existing connection was forcibly closed by the remote host." exception during runtime
  * What translations does NecroBot support?

## Why is NecroBot requesting an email and password instead of Google OAuth token?

Niantic changed the way that PokemonGO authenticates with the Google service which stopped supporting the OAuth service that FeroxRev's PokemonGO API was using. If you have security concerns over using your Google account for this, then create a PTC account or look through the source code yourself and compile the program yourself.

Please refer to Necro's response below. Other bots who share the same API have chimed in too: https://www.reddit.com/r/pokemongobotting/comments/4v3v8y/necrobot_security_warning/d5vvgy9?st=ir81ibx9&sh=e2e5baff

## Every Pokemon I try to catch returns CatchFlee and I cannot claim any Pokestops.

Your account has been softbanned because your account has travelled too far to too short of a time window. The length of the soft ban depends on the distance that you traveled which can be anywhere from 5 mins to 3 hours. Check your new location every 30 minutes until you can successfully catch Pokemon again.

How do I run NecroBot without any prompts?

Set StartupWelcomeDelay to false. This setting is default to true to prevent people from locating to the wrong locations by mistake.

## Can I still login to my account on the Pokemon GO app while NecroBot is running?

Yes! Only if you turn off Location services or GPS on your device while the PokemonGO app is in use. Otherwise you will be soft-banned by Niantic. With GPS turned off, you will only be able to manage your Pokemon and items, but it is better than nothing. You will not be able to spin Pokestops or catch Pokemon in the app.

## When I try to build the source code, I receive a "One or more projects were not loaded correctly" error

You must download the Rocket API release ZIP file and extract it into the Necro-bot directory. Follow steps #2-4 again

## How do I run multiple bots at once?

Create different directories that each have their own installation and run each of their .exe. If you plan to create a script that runs them, make sure the current working directory in your console is the root of each NecroBot's installation.

## When I launch the .exe after setting my configurations, the app immediately crashes and displays a bunch of JSON reference exceptions

If you see a screen similar to below and your log file only has Initializing Rocket logger at time, then your config.json or auth.json file has a typo. Scrolling up in console window will show the exact parsing error on the first line.

http://i.imgur.com/TCrWpse.png

## How do launch the Google login process again to change accounts?

Delete the GoogleRefreshToken value from the /Auth.json file from the Configs directory. Also make sure that you are logged into the Google account in your default browser.

## After I paste my device code into google.com/device, Necro-Bot logs into the wrong account. How do I log into the right account?

Necro-Bot opens the google.com/device URL in your default browser and based on your cookies, it may select a different account than you expect. Make sure the browser that you type the code into is logged into the correct account.

## How often does the bot evolve Pokemon, recycle items, or rename Pokemon?

Every 5th PokeStop it spins.

## How does egg hatching work?

As long as you are under 20 kmph, the eggs will hatch automatically when they are ready to hatch. There is no indication in the bot to show hatches. To incubate an egg, you must log into the app. The bot may auto-incubate eggs in the future.

## How do I use Lucky Eggs before the bot evolves Pokemon?

Set useLuckyEggsWhileEvolving to TRUE in the settings. By default, this is set to FALSE.

## How can I use incense, lucky eggs, and incubators?

Open the app on your device with location turned off (to prevent a softban) and manually trigger the item. This may change in the future with a feature.

## How do I ignore to catch a Pokemon?

Set UsePokemonToNotCatchFilter to TRUE and add the Pokemon to your Config/ConfigPokemonsNotToCatch.ini file

## Why is my bot recycling items?

In order to prevent the inventory from getting too full, the bot will automatically recycle items based on the values defined in the Config/ConfigItemList.ini file.

## Why are some Pokemon not being transferred?

Any pokemon that meets the below criteria is transferred:

Total number of that pokemon species in your invetory is greater than KeepMinDuplicatePokemon
Below the KeepMinIVPercentage value
Below the KeepMinCP value
Is not listed in your ConfigPokemonsToKeep.ini config file
If KeepPokemonsThatCanEvolve set to True, you will keep a number of that species based on the number of candies you have. See the below FAQ entry.

## Why do I receive the "(ATTENTION) PokemonInventory is Full. Transferring pokemons..." error over and over?

If you have KeepPokemonsThatCanEvolve set to True and EvolveAllPokemonWithCandy set to False, the bot may have no way to transfer the massive amounts of Pokemon it is hording based on the number of species candies you have.

This can also occur if KeepPokemonsThatCanEvolve set to True and EvolveAllPokemonWithCandy set to True, but your PokemonsToEvolve list does not include the Pokemon that is filling your inventory that you have a ton of candies for since NecroBot will never evolve the Pokemon.

For example, if you have 600 Pidgey candies, the bot will keep 50 Pidgey's in your inventory before it will start transferring.

## Why do I receive the "(ATTENTION) Encounter problem: Lure Pokemon NotAvailable" error?

When a Pokestop is lured a Pokemon spawns on an interval, NecroBot can see what Pokemon will spawn, but it may not have spawned yet due to the interval. If the interval hasn't expired, you will get the pre-mentioned error message.

Effectively this can be ignored.

## I have so many candies for one Pokemon and I want to use them for experience farming. How do I do that?

  * Set KeepPokemonsThatCanEvolve to true
  * Set EvolveAllPokemonWithCandy to true
  * Add the Pokemon to evolve to your PokemonsToEvolve list
  
Every time NecroBot evolves, it will evolve as many of that Pokemon limited based on the number of Pokemon and candies that you have.

## Why are PokeStops not being loaded in the console?

If your console looks like in the image (https://i.imgur.com/WRIyYu7.png), the servers in that area are unstable. Try a different location or try again later.

## My Bot is repeating DisplayHighestCP

One of your Config Files has a typo.

## Why is this Bot a bit slower than others?

We are using a Humanizer, doesnt spam the Servers & hopefully will help in a banwave

## What does IV mean?

Here (https://www.reddit.com/r/TheSilphRoad/comments/4tzcmk/faq_on_ivs_info_megathread/)is a Reddit post that will explain it all.

## Where can I find the change location?

Right here (#).

## How do I know which radius value to use?

Visit https://www.freemaptools.com/radius-around-point.htm, this website will help you out!

## I receive a "Value of parameter must be between -90,0 and 90,0" error when running the bot

Change the delimiter for lat/long within the .gpx file or config file from comma to period or vice versa

## How do I configure the bot to not catch any Pokemon?

Set UsePokemonToNotCatchFilter to true in config.json and add the values from the below PasteBin to your PokemonsToIgnore in your config.json file in the Config directory: http://pastebin.com/raw/AyEwTBcT

## I received a "An existing connection was forcibly closed by the remote host." exception during runtime

If you receive the below exception, this could indicate that the Pokemon GO servers may be unstable or that your internet connection is unstable. Try again later.

System.Net.Http.HttpRequestException: An error occurred while sending the request. ---> System.Net.WebException: The underlying connection was closed: An unexpected error occurred on a send. ---> System.IO.IOException: Unable to read data from the transport connection: An existing connection was forcibly closed by the remote host. ---> System.Net.Sockets.SocketException: An existing connection was forcibly closed by the remote host

## What translations does NecroBot support?

Navigate to the Translations folder in your NecroBot installation directory and that should show a list of files of the different languages it supports.

_https://github.com/DNA64/NecroBotWiki_
