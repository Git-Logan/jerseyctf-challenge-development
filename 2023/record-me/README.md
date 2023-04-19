# record-me - easy 

## Description
* I deleted TikTok a few years ago due to privacy concerns. I decided to spend more time on Instagram Reels... ironic isn't it? Quick! Record me for my Reel. Good video, let's post it. Ah shoot, what is my password... can you help me find it? I remember I **record**ed it somewhere in www.jerseyctf.com.

## Hint
* What is 8.8.8.8? 

## Solution Steps
* Use any of the following dig, nslookup, or host commands to search the DNS records of www.jerseyctf.com:
  * dig www.jerseyctf.com txt
  * dig -t txt www.jerseyctf.com +short
  * host -t txt www.jerseyctf.com
  * nslookup -type=txt www.jerseyctf.com
* Flag: `jctf{hop_OFF_TIKTOK_and_GET_s0me_SUN_OUTSID3!}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1590.002 - Gather Victim Network Information: DNS](https://attack.mitre.org/techniques/T1590/002/) 
