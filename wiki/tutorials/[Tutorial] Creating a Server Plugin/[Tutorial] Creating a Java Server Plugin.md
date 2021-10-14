## Notice:
## Creating a Java Server Plugin
**Complete the [Creating a Java Mod](../wiki/%5BTutorial%5D-Creating-a-Java-Mod) Steps 1-4**.
### Adding custom commands
In order to register server player commands, you most override the `registerClientCommands(CommandHandler handler)` Method.  
Using UPPERCASE letters in command name somehow breaks the command, don't do it.  
*Note: registering a command when the command name was already used will override the previous command.*
```java
public class CustomMod extends Plugin {
    @Override
    public void registerServerCommands(CommandHandler handler) {
        handler.register("name", "description", (args, player) -> {
            Log.info("ok");
        });
        handler.register("name", "<required> [optional...]", "description", (args, player) -> {
            //stuff
        });
    }
    
    @Override
    public void registerClientCommands(CommandHandler handler) {
        handler.<Player>register("name", "description", (args, player) -> {
            //stuff
        });
        handler.<Player>register("name", "<required> [optional...]", "description", (args, player) -> {
            //<required> something must be typed after command
            //[optional] something may be typed after command
            //<required...> or [optional...] argument may contain spaces (can only be last argument e.g. not <required...> [optional])
            if (args.length == 1) {
                player.sendMessage("<" + args[0] + ">");
            } else {
                player.sendMessage("<" + args[0] + "> [" + args[1] + "]")
            }
        });
    }
}
```
### Control Player Actions
In order to control player actions, stop them from building for example, you must add a `actionFilter`.  
You can register a action filter adding your filter to the actionFilter list in `Vars.netServer.admins`.

Servers will check the actionFilters in the order they were inserted.  
If the runnable returns true, the server will check the next actionFilters, if false, the action is denied.  
If a actionFilters denies an action (return false) the rest of the action filters won't be triggered.  

*Note: denying a configuration for node config will cause client-side de-sync.*  
```java
Events.on(EventType.ServerLoadEvent.class, event -> {
    Vars.netServer.admins.addActionFilter(actionFilter -> {
        return !unverifiedPlayer(actionFilter.player);
    });
});
```
