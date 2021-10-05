### Call
**Call.sendMessage(String message);**  
Send a message to everyone in chat.  
Example:  
```java
Events.on(EventType.PlayerJoin.class, event -> {
    Call.sendMessage(event.player.name + " [white]has joined!");
});
```

**Call.infoMessage(String message);**  
Sends a Dialogue Message to everyone.
### Groups
**Groups.players;**  
Sends a list of all connected players.  
Example:
```java
public static void listAllPlayers(Player player) {
    for (Player p : Groups.player) {
        player.sendMessage(p.name + " [white](" + p.id + ")");
    }
} 
```
### Vars
**Vars.state**  
Returns GameState, which contains data such as current maps, amount of enemies and rules of this map.
Example:
```java
public static void mapInfo(Player player) {
    StringBuilder builder = new StringBuilder;
    builder.append("Map Name: " + Vars.state.map.name());
    builder.append("\nMap Author: " + Vars.state.map.author());
    builder.append("\nMap Wave Spacing: " + (int) (Vars.state.rules.waveSpacing / 60) + "s"); //waveSpacing is measured in ticks, server tps is 60/s
    player.sendMessage(builder.toString());
}
```