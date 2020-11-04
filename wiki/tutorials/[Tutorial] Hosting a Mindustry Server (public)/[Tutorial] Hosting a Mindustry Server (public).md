Prerequisites:
You have completed the guide to creating a local server, and you have access to your router.

### Step 1) Find your devices local IP. 
It varies between devices, but you might be able to find it with that device.
Windows: `ipconfig` and find the line that says "IPv4 Address."
Linux: `hostname -I`
### Step 2) Setting up port forwarding:
Here's [a guide](https://www.noip.com/support/knowledgebase/general-port-forwarding-guide/) for port forwarding on common routers.
You will need to set it up to forward port 6567, on TCP and UDP, to the IP you found last step.
### Step 3)
That's enough to access a server from the internet. Now just go to [this website](https://ipv4.icanhazip.com/) to get your public ip. Note that this changes.
In Mindustry, just add a server and input the ip you got. You should be able to share that IP with other people, but it will change unless you have a static IP. If you don't know, you probably dont. To fix that, you will need to set up a free dynamic ddns. You can get that [here](https://www.noip.com/). They have a guide on the website, just set up port 6567 similar to the router.
