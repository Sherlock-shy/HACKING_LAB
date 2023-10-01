<h1>Virtual machine hacking lab</h1> 
Making a lab for practicing any cyber skills

inspire by: https://www.youtube.com/watch?v=mvsiuLzpx2E

<h2>Environment used</h2>

- Oracle VM Virtual Box(Kali Linux)<br>
  Link: https://www.virtualbox.org/wiki/Downloads
- Vulnhub Mr. Robot<b>(Not recommended, reason will be state out later)</b><br>
  Link: https://vulnhub.com/entry/mr-robot-1,151/
<h2>Steps go through </h2>

step 1 download and install virtual box adn virtual box extension manager<br>
step 2 download kali linu and the vulnerable machine<br>
step 3 connect them together <br>
step 4 Make their network isolated <br>
step 5 Start hacking(As this is just set up, the walk through will be write in another repositories) <br>

<h2>Walk through</h2>

<h4>Downloading and set up the Virtual box</h4>

![image](https://github.com/Shecklock/HACKING_LAB/assets/84926502/18f3cb0d-c9d9-4362-a9cc-9102a59a5ff2)<br>
Start by downloading the VM, I am using the [Virtual Box](https://www.virtualbox.org/wiki/Downloads). 

![螢幕擷取畫面 (293)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/f0a7e01c-b705-4cd7-b276-2319e8302019)

<h3>Problem encountered</h3>

After the downloaded, the VB said I am missing the dependencies Python Core / win32apipywin3, I have to install it first manually so i can avoid it have bug later(If install before having the pywin32, i have to manually set up later)
![image](https://github.com/Shecklock/HACKING_LAB/assets/84926502/46a3cc2d-e9e5-4d69-a796-6e01fdd633cb)
<br><b>(note: I forgot to screenshot, this is a photo from the user [Sanjith-R-Warrier](https://kodekloud.com/community/t/missing-dependencies-python-core-win32api/215281), I am using this image for demonstration only)

<h3>Solution</h3> 
First, go to install Python from https://www.python.org/downloads/
And excute the code "pip install pywin32" on the command promt to install, normally this will solve the problem <b>IF YOU ARE EXCUTING THE COMMAND IN THE RIGHT PATH</b>(which I am not)<br> 


<h4>Downlaoding and set up the Vulnable machine</h4>
Windows defender said it have virus Trojan:Win32/Casdet!rfn)
i decided to downlad the file in my backup laptop so it won't affect my main computer, and check for the file hash (MD5/SHA1)to ensure the file integrity from vulnhub using powershell command "get-filehash -algorithm MD5 ./Downloads/mrRobot.ova"
