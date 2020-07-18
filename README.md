<sup>_A Spigot/Paper Plugin | Native Minecraft Version: 1.16_</sup>
# Jake's Random Teleporter `[J-RTP]`
What does it do? • Teleports a player to a random location by when they type `/rtp` or `/wild`, or when they join the server for the first time • Tons of configuration from basic shape and size to multiple configs and distribution patterns

## A brief list of what you can configure.
* Which worlds the config is enabled in
* What shape that the points will appear in...
    * Square
    * Circle
* The maximum distance to take a player from the center
* The minimum distance to take a player from the center
* Where the random teleport is centered...
    * At the world's spawn
    * At the players current location`
    * At a specific x and z
* Will the locations be chosen such that they are evenly distributed or with a Gaussian distribution...
* If Gaussian distribution is enabled, these settings can be used:
    * Shrink - Inversly related to the standard deviation of the distribution (larger values make it denser)
    * Center - A number from 0 to 1 where 0 centers the points at the min distance, 0.5 is between min and max, 
    and 1 is at max
* The number of seconds a player must wait before using the /rtp command again
* Do new players get teleported randomly when they join for the first time? *
* The lowest y-value that a player can get teleported to
* Some stuff about how many spots to check for safety, though these shouldn't need to be modified for a normal world.
###### _* <sub>Denotes static settings. (Settings that are not per config, and generally are only applicable to one config at a time)</sub>_
###### _All of this is per individual config. Multiple configs can exist at the same time_

Oh, and if you want more than one config, you just copy and paste the config section, change the name, and suddenly you have 2! An example of this is sitting at the bottom of the default generated config.

## The config (and all its documentation)

Go [here](src/main/resources/config.yml) for the config,
or [here](doc/config.md)


## Random points examples
The random coordinate generator I made for this plugin does a real good job at evenly distributing points over an area, assuming you _want_ them to be distributed evenly.
You can choose from having the points evenly distributed throughout the given area, or have a Gaussian distribution where the points are more densely distributed around a specific radius.
Here are some examples of possible distributions, though it is worth noting that every value can be changed, and these are far from the only options. 
The examples displayed are just to give an idea of what the settings can do.
![Image](pics/distributionExamples.png "icon")


#### Here are some settings that I like.
Both of these have a relatively consistent distribution towards the middle and inside (while still leaving a gap for spawn),
but they also make it so that player will _not_ frequently be placed near the max distance. 
While the distribution of rtp locations is not something people tent to focus much on, it may still be fun to get that
one off rtp that takes you further out that most others do.

| Using a circle...       | Using a square...       |
| ----------------------- | ----------------------- |
| ![Image](pics/x%20Circle%20250%20to%201000%20-%20Normal%20distribution%20(4-0.25).png "icon") | ![Image](pics/x%20Square%20250%20to%201000%20-%20Normal%20distribution%20(4-0.25).png "icon") |
###### All images made with points generated by the plugin, and plotted with gnuPlot.

## Permissions
* jakesrtp.use
    * description: Allows the use of the base "/rtp" command
    * default: true
* jakesrtp.rtpondeath
    * description: If rtp-on-death is enabled, players with this node will be respawn in a random location
    * default: false
* jakesrtp.noCooldown
    * description: Allows the user to ignore the cool-down timer
    * default: op
* jakesrtp.others
    * description: Allows the use of "/rtp" on other players
    * default: op
* jakesrtp.admin
    * description: Allows the usage of the "/rtp-admin" command.
    * default: op
    
Please go [here](src/main/resources/config.yml) for the config.


## Commands
`/rtp` and `/wild` both make the user randomly teleport  
`/rtp [playerName]` will randomly teleport the given player (assuming you have permission)
`/rtp-admin` reload will reload the config from the file(assuming you have permission)