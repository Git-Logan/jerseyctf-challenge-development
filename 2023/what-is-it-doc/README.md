# what-is-it-doc - easy 

## Description
* AI can now get infected with malware! After asking ChatGPT for a tomato soup recipe, recipe.pdf was provided.
* After running the command **md5sum recipe.pdf > result.txt** and opening result.txt, we see an interesting string: f8b604ca7aa304a479f2461d1b74e795
* Is ChatGPT sick? jctf{popular threat label}

## Hint
* https://www.mcdonalds.com/us/en-us/product/hash-browns.html

## Solution Steps
* Open the [VirusTotal](https://www.virustotal.com/gui/home/search) website and navigate to the Search tab.
* Copy the provided MD5 hash into the search bar, which results in getting malware information about the BlackKingdom ransomware trojan.
* Flag: `jctf{trojan.blackkingdom/blackin}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1204.002 - User Execution: Malicious File](https://attack.mitre.org/techniques/T1204/002/) 
* [VirusTotal](https://www.virustotal.com/gui/home/search)
