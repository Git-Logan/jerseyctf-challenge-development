# jack-and-jill - easy 

## Description
* Jack and Jill went up the hill; To fetch a pail of... cipher?
* pgQVJFCohpccuyBSbwxcxpVZCAATRT

* | 3 9 | (first row) <br>
* | 4 7 | (second row)

* jctf{plaintext}

## Hint
* "Unfortunately, no one can be told what the Matrix is. You have to see it for yourself."

## Solution Steps
* Identify that the type of cipher that requires a matrix is called a Hill cipher. This can be Googled: "type of cipher that uses a matrix"
* Using [dCode](https://www.dcode.fr/hill-cipher), copy and paste the ciphertext into the text box along with the provided matrix values.
* It is also possible to solve this [manually](https://youtu.be/JK3ur6W4rvw).
* Flag: `jctf{hiTHEREwelcomeTOlinearALGEBRAZ}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1140 - Deobfuscate/Decode Files or Information](https://attack.mitre.org/techniques/T1140/)
* [Hill Cipher](https://en.wikipedia.org/wiki/Hill_cipher)
* [dCode](https://www.dcode.fr/hill-cipher)
