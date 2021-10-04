### Call
**Call.sendMessage(String message);**  
Send a message to everyone in chat.  
Example:  
```
Events.on(EventType.PlayerJoin.class, event -> {
    Call.sendMessage(event.player.name + " [white]has joined!");
});
```

**Call.infoMessage(String message);**  
Sends a Dialogue Message to everyone.
