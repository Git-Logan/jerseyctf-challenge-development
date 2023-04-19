# recover-the-cure - medium 

## Description
* There is a worm taking over Skynet 0.5 and a cure is needed A.S.A.P.! Donnie Rodgers was The Chosen One, but he got mad and deleted the cure from his computer with a quick **rm** command. We were luckily able to create a forensic image of the hard disk before he went off the grid.
* Data is never truly deleted unless... you demagnitize the hard drive, destroy it with a hammer, and throw it in the Atlantic Ocean. Assuming Donnie didn't follow those steps, is there a way we can search for remnants of the deleted cure information?
* These are all the same 1.46GB file, only need to download from one of the links - 
    * [Download Link #1](https://drive.google.com/drive/folders/1hAXTpbxNjuiJ2FebxZOEfNU-U4bNZDy5?usp=sharing)
    * [Download Link #2](https://drive.google.com/drive/folders/1VOZL_nphqEH20fxPnuDHPbyX0UXBuHnp?usp=sharing)
    * [Download Link #3](https://drive.google.com/drive/folders/1kuvGabNr-rwwcnzdRYxFHh75IeFigugV?usp=sharing)

## Hint
* No need to virtualize anything.
* There are multiple ways to find this flag, some easier than others. The point of this challenge is to give you experience using a fancy and *free* digital forensics tool!

## Solution Steps
* Download the donnie.E01 file and acknowledge that it is an EnCase forensics disk image file based on its file extension, which can be opened in the popular digital forensics tool [Autopsy](https://www.autopsy.com/).
* After opening the image in Autopsy, there are a few things that you can type in the Keyword Search box to try to find the flag. This includes `jctf`, `flag.txt`, or `cure`, which are all based on the provided description breadcrumbs.
* The flag will be revealed in these files: `Q`, `Unalloc_197938_603865088_6428164096`, and `swapfile`.
* Flag: `jctf{the_cure_is_in_your_heart_<3}`

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1005 - Data from Local System](https://attack.mitre.org/techniques/T1005/) 
* [MITRE ATT&CK® Technique T1485 - Data Destruction](https://attack.mitre.org/techniques/T1485/) 
* [Autopsy](https://www.autopsy.com/)
