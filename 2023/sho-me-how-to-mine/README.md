# sho-me-how-to-mine - medium 

## Description
* Check out our Minecraft Java Edition server! Find it using [Shodan](https://shodan.io).  
* [Shodan](https://shodan.io) is a search engine that allows users to passively search for devices connected to the Internet worldwide.
* **IMPORTANT**: Shodan’s search results are real-life hosts. This flag needs to be found using completely legal, passive reconnaissance methods to gather OSINT on Shodan. Do not use any illegal or active reconnaissance methods for this challenge. There are a limited number of searches whether you have an account or not, so make each one count! Signing up for a free account or with a .edu email provides you additional features and searches.

## Hint
* What are we capturing in a CTF?
* Submit with jctf{}

## Solution Steps
* Pick key words from the challenge text to build a query, specifically `Minecraft Java Edition server`
* Research [Shodan search filters](https://www.shodan.io/search/filters) and also the port that Minecraft Java Edition runs on.
* In Shodan, search `flag port:25565`
* Click on the 143.244.151.174 host with the JerseyCTF lock server icon and read the flag in the Minecraft server MOTD.
* Flag: `jctf{mining_s1nc3_2011!}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1596.005 - Search Open Technical Databases: Scan Databases](https://attack.mitre.org/techniques/T1596/005/) 
* [Shodan](https://shodan.io)
