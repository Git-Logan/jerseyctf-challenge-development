# parts-of-a-pair - medium 

## Description
* Donnie Rodgers has escaped The Matrix! His final wish is for you to access his secret credentials that are encrypted using public key (asymmetric) cryptography. These credentials have a special message that needs to be sent through Skynet 0.5 ASAP! Before going off the grid, he created an account for you to remotely access his system to locate this information.
* `ssh <username>@<host>` | Password: `<password>`

## Hint
* Donnie Rodgers failed his information security training at work a record 9 years in a row and was a believer in "security through obscurity." 

## Solution Steps
* SSH into the system and perform an `ls -a` command to list all of the directories. Two notable hidden directories include the [.gnupg (GNU Privacy Guard)](https://www.gnupg.org/gph/en/manual/c481.html) and [password_store](https://www.passwordstore.org/) directories.
* Change directories into .gnupg. We can see some keys and other important files, the one missing thing is the passphrase used to decrypt the private key. Good information security practices have the private key never exposed.
* Change directories into .password-store. We have a file called flag.gpg, but it is encrypted.
* Navigating back to the home directory and into the Desktop directory, there is a hidden sticky note file called svchost.snt in the Desktop directory which has the passphrase needed - `characterWORDworth8!`. Good information security practices have this passphrase stored off this computer in a more secure manner. This passphrase is the "second layer" of protection that GPG offers if a private key is leaked.
* Use the command `pass flag` to decrypt the private key and unlock the vault for the flag.
* Flag: `jctf{protect_PRIVATE_KEYS_and_dont_STORE_passwords_ON_a_STICKY_N0TE}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1552 - Unsecured Credentials](https://attack.mitre.org/techniques/T1552/) 
