Prerequisites:
In order to host a server, You need a machine or [VM](https://en.wikipedia.org/wiki/Virtual_machine) with atleast 2 cores and 1024MB of [ram](https://en.wikipedia.org/wiki/Random-access_memory).  
(Linux) Make sure all files being executed have proper permissions. Tutorials [here](https://www.guru99.com/file-permissions.html) and [here](https://www.tutorialspoint.com/unix/unix-file-permission.htm).

### Step 1) Getting the main server files:  
The main server files (named server-release.jar) can be downloaded from [here](https://github.com/Anuken/Mindustry/releases).  
* [v5.0 - v105.6](https://github.com/Anuken/Mindustry/releases/tag/v104.6) is an old version of Mindusry.
* [v6.0 - v126.2](https://github.com/Anuken/Mindustry/releases/tag/v126.2) is the latest stable release of Mindustry. This is the most popular version.  
* [v7.0](https://github.com/Anuken/Mindustry/releases/) is the latest experimental of Mindustry. This is a experimental version of mindustry, said to be released as soon as winter 2020.

### Step 2) Setting up the server files:  
In order to run the server, one must execute the server-release.jar. Before doing so, it is recommended to place the server on a empty folder.  
For installation of [Mods](https://github.com/topics/mindustry-mod), [Custom Maps](https://steamcommunity.com/workshop/browse/?appid=1127400&requiredtags[]=map) and more check step [#5](#step-5-Setting-up-server).

### Step 3) Dependencies:
In order for the server to run, [Java RE/JDK 1.8](https://www.oracle.com/java/technologies/javase-jre8-downloads.html) must be installed.  
(Windows) Make sure that the path for the java 1.8 is properly included in the Windows Environmental Variables.  
(Linux) unknown, do your own research. 

### Step 4) Running your server:
There are a few ways from running your server.  
  
**(W & L) Running server directly through CMD:**  
cd ([windows](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/cd)/[linux](https://linuxize.com/post/linux-cd-command/)) to the server directory. Use Java command `Java -jar server-release.jar` and watch the server start up. 
 
**(Windows) Batch file:**  
A [Batch file](https://www.windowscentral.com/how-create-and-run-batch-file-windows-10) can be used to run servers. A batch file can be coded such that it runs the server once or relaunches every time the Mindustry Server crashes.  
\* Must be placed in the same folder as server-release.jar  
Launch once example [here](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(local)/server.bat).  
Automatic Relaunch example [here](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(local)/server%20auto.bat).

**(Linux) Scripts:**  
A Script can be used to run servers. A Script can be coded such that it runs the server once or relaunches every time the Mindustry Server crashes.  
\* Tutorial on Linux Script's [here](https://www.cyberciti.biz/faq/howto-run-a-script-in-linux/).  
Automatic Relaunch example [here](https://github.com/Anuken/Mindustry/blob/master/server/run-jar).  

**(W & L) [Advanced] Java Program:**
A Java program can be used to run servers. A java program can be used to Automatically manage server files.  
Possibilities include: Running Server with higher Priority, Managing: Maps, Plugins, Mods and Rules.  

### Step 5) Setting up server:
Now that your server can run, we must set it up.  
**Basic:**  
Use the following commands in server console to configure your server.  
* config - List of Configurations, such as name, port, description etc.  
e.g. `config name Awesome Server` `config port 1000`

**Advanced:**  
Use the following commands in server console to configure your server.  
* rules - Change game values such as player damage. List of rules can be found [here](https://github.com/Anuken/Mindustry/blob/master/core/src/mindustry/game/Rules.java).  
e.g. `rules add unitHealthMultiplier 2` `rules remove blockDamageMultiplier`

If you ran your server atleast once, a config folder should've been created.  
The config folder should contain:  
maps folder - Place Custom Maps here so they appear in the map rotation.  
mods folder - Place Plugins and/or Mods here.  
\* If Modded, Players require the mods to be installed before being able to join.

### Step 6) Starting Mindustry server:
To start a Mindsutry server, one msut first start the server, then host a map and gamemode.  
**Manual:**  
To Manually host a map, use command `host <mapName> [gamemode/survival if empty]` to host Mindustry server.  
Use command `maps` to get a list of map names.  
Game modes include Survival, Attack, PVP and Sandbox.  

**Automatic [Advanced]:**  
To automatically host a map, a special command must be used.  
The configuration `startCommands` in `config` allows the server to run a sequence of commands upon being launched.  
e.g. `config startCommands host <mapName> [gamemode]` `config startCommands Tendrils survival`


## Local server should be good to go!
Your local mindustry server should now be good to go! Players on your same network should be able to join.  
In order to connect to the server, try searching for it in the `Local Servers` tab and if that doesnt work, add the server directly by clicking `add server` then typing `serverIP:port` (replace words with their respective values).

### How can my friends connect through the internet to my server?
Check the public tutorial [here](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(public)/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(public).md)
