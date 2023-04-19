# what-are-the-odds - medium

## Description
* A biomedical engineering company would like to develop an artificial intelligence (AI) program to automatically perform monthly risk assessments on their medical devices to safeguard patient safety and personally identifiable information (PII) for HIPAA compliance.
* An infusion pump they manufacture comes with an offline web application that can be used by nurses to adjust fluid pump rate for patients, which is something to consider if it gets into the wrong hands. Access to the application is protected by an 8-digit PIN. Even though the company deploys the principle of least privilege in all systems, the risk assessment still considers insider threats.
* The AI prototype has calculated what the likelihood of a successful threat event is with the current minimum PIN length and lockout policies for a trial risk assessment and the developers are asking you to see if it is correct.
* Starting with a random 8-digit PIN, each element in the set being {0,1,2,...,9}, and the lockout policy limited to 3 unique attempts, what is the worst-case probability that an insider threat can successfully guess the PIN and log in to maliciously alter the fluid pump rate?
* jctf{decimal} or jctf{percent}

## Hint
* It is always fun to see how many unique combinations there are!
* For Learning Purposes - [NIST 800-30 Guide for Conducting Risk Assessments - Section 3.2](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf#%5B%7B%22num%22%3A102%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22XYZ%22%7D%2C88%2C720%2C0%5D)
* For Learning Purposes - [Health Insurance Portability and Accountability Act of 1996 - HIPAA](https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html)

## Solution Steps
* In the set {0,1,2,...,9}, there are 10 possible values which can be placed in 8 different places, so 10^8 leads to 100,000,000 possible combinations.
* 1st attempt - 1/100,000,000. 2nd attempt - 1/99,999,999. 3rd attempt - 1/99,999,998 = The probability is 0.00000001 or 0.000001%. 
* Flag: `jctf{0.00000001}` or `jctf{0.000001%}` or `jctf{1.00000002e-8}` or `jctf{1.00000002x10^-8}` or `jctf{0.0000000100000002}` or `jctf{0.00000100000002%}` or `jctf{.00000001}` or `jctf{.000001%}` or `jctf{.0000000100000002}` or `jctf{.00000100000002%}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1110.001 - Brute Force: Password Guessing](https://attack.mitre.org/techniques/T1110/001/) 
* [NIST 800-30 Guide for Conducting Risk Assessments](https://csrc.nist.gov/publications/detail/sp/800-30/rev-1/final)
* [AAMI TIR57 Principles for Medical Device Security - Risk Management](https://webstore.ansi.org/standards/aami/aamitir572016)
* [Health Insurance Portability and Accountability Act of 1996 - HIPAA](https://www.hhs.gov/hipaa/for-professionals/security/laws-regulations/index.html)
