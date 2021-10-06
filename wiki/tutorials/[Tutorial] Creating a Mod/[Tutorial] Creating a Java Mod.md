## How to create a Java Mod
Prerequisites:  
You must have [IntelliJ](https://www.jetbrains.com/idea/download/), [Eclipse](https://www.eclipse.org/downloads/) or any other [Java IDE](https://www.google.com/search?client=opera-gx&q=java+IDE) installed on your machine.  
You must have [Java 8](https://www.google.com/search?q=java+8+download) or higher.

*Authors Note: AFAIK the only difference between a mod and a plugin is that mods add new content or modify existing content* 

### Step 1) Getting the Mod Template
The first step is getting the Mod Template. The mod template usually contains the following:
* Gradle Files
* Basic Source Code
* JSON/HJSON mod/plugin file
* `.gitignore` file

These files are essential in order to create a mod and properly share it on GitHub.

### Step 2) Setting up the IDE
*This is my experience with IntelliJ, if you use a different IDE your experience may vary*

Your first step is to import the "Project" aka the Mod Template.  
Once the project is loaded, your IDE should detect it's a gradle project and automatically start downloading the required dependencies.  
Make sure your project level language (Java Version for Mod) is set no higher that what the Mod Template set for.  
e.g. Anuke's [Mod Template](https://github.com/Anuken/MindustryJavaModTemplate) intends for Java 16 or lower to be used.

### Step 3) Making sure you can compile
It is really important you try to compile the Mod Template before you start modifying it.  
This way you can make sure you can compile working code instead of troubleshooting whether your code is causing compile to fail.

Steps on how to compile can be found in the Mod Template's Readme.md  
If no instructions are provided, you can look inside the build.gradle for any tasks such as jar, dist, deploy, etc. and use the terminal command `gradle <task>`.  
You should find your mod file in `<modDirectory>/build/libs/`.

### Step 4) Time to modify
Now that you have the Mod Template and made sure it compiled, you can start making the mod folder your own.   

You can start by modifying the mod's data file (mod/plugin.json/hjson) so it contains the proper info such as name, author etc.  
You can also change the packets name (folder inside `src/`) to whatever you like. (Make sure to change it in mod's data file too)

Now that the mod has been set up, you can start looking inside Mindustry's src for methods you may want to use.
Some files you can search include but are not limited to `Call.java`, `Vars.java`, `Events.java` (`EventType.java`) and `Groups.java`.  
Go [here](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Creating%20a%20Mod/FrequentlyUsedMethods.md) to find Frequently Used Methods.

###Step 5) Add new Content
*Note: Multiplayer will require all players to download the mod before being able to join*  

In order to load content, Items Liquids Blocks Etc., you must create a class that implements ContentList.
```java
public static class CustomItems implements ContentList {
    public static Items Anukium;
    
    @Override
    public void load() {
        Anukium = new Item("anukium", Color.valuueOf("ffffff")) {{
            hardness = 15;
            cost = 100f;
            radioactivity = 7.5f;
        }}
    }
}
```
And then loading your custom `ContentList` by overriding the `Mod.loadContent()` method.
```java
//CustomMod.java
public class CustomMod extends Mod {
    //Other stuff here
    @Override
    public void loadContent() {
        new CustomItems.load();
    }
}
```