## Notice: 
**You must complete the [local server tutorial](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(local)/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(local).md) prior to starting this tutorial!**
##Disclaimer:
**For those planning to host servers from your home network**
- Hosting public servers may be violating your [ISP's](https://www.investopedia.com/terms/i/isp.asp) Terms of Service which could lead to extra fees and charges to your monthly plan.  
- Depending on your contract, you may have a data cap limiting how much data you can receive and send. Going over this limit *may* cause additional fees and charges to your ontly plan.  
- If you plan on sharing the ip/domain of your server, be aware that not only your IP can be used to locate where you live, but can also allow malicious individuals to configure with your router as long as it uses a generic username / password.  

These things are unlikely to happen, but you must be aware of the dangers associated with opening ports and publicly sharing your ip to others.   

If you only plan on hosting a server for you and your friends, these risks are greatly reduced but remain true nonetheless.

## How to Host a public Mindustry Server:
### Step 1) Configuring your router
If you are hosting from a Remote Server (Such as Linode, Azure, etc.), you can skip this section and proceed to [Step #3](#step-3-getting-a-proper-dns)

There are 2 things you need to do in order to properly port forward.
1) Make your server's local ip static
2) Port forward your desired port

The best way to make your server's local IP static is by configuring it in the router's setting.  
This varies router to router, so you have to experiment a bit.  
Example: [tplink](https://github.com/L0615T1C5-216AC-9437/ChaoticNeutral/blob/master/wiki/tutorials/%5BTutorial%5D%20Hosting%20a%20Mindustry%20Server%20(public)/PortForwarding-tplink.md)  
(windows) to get your internal, open CMD, run ipconfig and select the ip next to ipv4
(linux) do ifconfig on terminal and get the one that says eth0

Next is Port Forwarding.  
Just like the previous step, port forwarding varies from router to router, so you have to experiment a bit.  
Your goal is to port forward port 6567, or the custom port you have chosen, to your server's local ip with both tcp & udp enabled for inbound and outbound

### Step 2) Opening your OS Firewall
This step is likely to be redundant  
(Windows) [Click here to see tutorial](https://www.tomshardware.com/news/how-to-open-firewall-ports-in-windows-10,36451.html)  
(Linux) [Click here to see tutorial](https://www.journaldev.com/34113/opening-a-port-on-linux)  

Open port 6567, or the custom port you have chosen, with tcp & udp enabled on both inbound and outbound

### Step 3) Getting a proper DNS
To simply put, a DNS is the 'name' of your IP. You may name your ip through free services such as [NoIP](https://www.noip.com) or by buying a domain.
You can learn more about DNS' by going [here](https://www.cloudflare.com/learning/dns/what-is-dns/)

## Your public server should be good to go!
Your public mindustry server should now be good to go! Players with your ip should be able to join.  
In order to connect to the server, try searching for it in the `Local Servers` tab and if that doesnt work, add the server directly by clicking `add server` then typing `serverIP:port` (replace words with their respective values).
