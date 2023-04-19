# securing-environments - medium 

## Description
* JerseyCTF infrastructure developers segment environments across a few different clusters - production, QA, testing, etc. This is essential so that new software versions and patches can be developed and tested offline before being deployed online with no downtime. 
* Something to consider in risk assessments is that this practice widens the company attack surface, as seen with the recent [LastPass security breach](https://thehackernews.com/2022/12/lastpass-admits-to-severe-data-breach.html). 

## Hint
* What are best practices for domain names of development/testing, staging, and production company environments?

## Solution Steps
* The answer to the hint is that "dev." is used in the subdomain for development environment domain names. This is either known already or can be Googled to find this [source](https://stackoverflow.com/questions/39336130/what-are-the-best-practice-for-domain-names-dev-staging-production) with the top answer providing this information.
* Navigate to https://dev.jerseyctf.com and then email jctf-testing-support-group@njit.edu for the Registration Code acting as a challenge developer, simulating social engineering.
* jctf-testing-support-group@njit.edu will auto-reply with a registration code. Register on the site with this and then look through the "test challenges."
* This real challenge will have its own "test" challenge listed and the flag will be leaked in the description.
* Flag: `jctf{dOnt_b3_LIK3_LASTp@ss}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1190 - Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190/) 
