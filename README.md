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
<br><b>(note: I forgot to screenshot, this is a photo from the user [Sanjith-R-Warrier](https://kodekloud.com/community/t/missing-dependencies-python-core-win32api/215281), I am using this image for demonstration only)</b>

<h3>Solution</h3> 
First, go to install Python(https://www.python.org/downloads/)
And excute the code "pip install pywin32" on the command promt to install, normally this will solve the problem <b>IF YOU ARE EXCUTING THE COMMAND IN THE RIGHT PATH</b>(which I am not)<br> 

![螢幕擷取畫面 (294)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/29c72197-37ce-4e18-8d0f-eedf1af55664)<br>
Translation for the chinese words:  ‘Pip‘ is Not Recognized as an Internal or External Command<br>

Thsi is may caused by the two reason here(research from [here](https://www.alphr.com/pip-is-not-recognized-as-an-internal-or-external-command/)):
- Reason #1: The Pip Install is <b>NOT</b> in the System Variable
  In order for Python commands to be executed from the Windows command prompt, the path to your pip installation will need to be added to the "PATH" system variable. It will be added automatically if you get Python through the installation file.<br>
  
- Reason #2: The Installation Was Not Added to Your PATH or System Variables
  If you added the path manually, the problem may be a typo. Missing a semicolon or  extra space somewhere will cause an error.<br>

In my case, the reason should be number 1 since I am not adding the path manually.<br>
Checking pip was added yo my PATH Variable, use the command 'echo %PATH%' in the command promt(win + r cmd)

![螢幕擷取畫面 (297)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/69597108-8b52-4405-9f0f-479adad749f2)

If the pip Install is in the system variable, it should show something like "C:\Python**\Scripts"(* = version of my Python) 
My python version is 3.11.5, i should get something like C:\Python3115\Scripts" which is not showing in the command promt

Searching for the python scripts file directly using my computer and i found it.

So my solution will be using the command directly in that directory:

![螢幕擷取畫面 (295)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/5f6c3809-76ae-43fa-9f35-89137dcb47f2)

Now i succesfully install the Virtual box:

![螢幕擷取畫面 (296)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/660b82b2-bab0-42b2-95e3-bcb37e19198d)

<h3>Downloading the Kali Linux & the Vulnable machine</h3>

Now download the VM for both our working console(Kali Linux) & the machine we are going to hack in

<h4>Downloading the Kali Linux VM</h4>

I am using the [Kali Linux](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/).
My download and import of the Kali Linux dose't have anything special happen, after downlaoded, just make the VM normally by clicking the NEW button in Virtual box.
But i got some problem with opening up since my pc didn't enable the VT-x(Intel Virtualization Technology)<br>
Enable it in the BIOS settings.

<b>BUT</b> i don't have the VT-x option in my BIOS settings.
I have looked a while and turns out I hvae to enable the option  "VMX", the CPU flag for Intel Hardware Vortualization. It is <b>exactly the same</b> for VT-x.<br>
At first i thought i have to enable the VT-d option as it is the only option i can found but turns out it is not the same thing<br>

Differenence:

VT-x is for the hardware virtualization<br>
while VT-d allows you to directly stream peripherals, such as PCI devices, which is not necessary in PC environment but very useful when running a server (vSphere server where you need a RAID card passed). directly to customers, etc.).<br>

After enable the settings, i can start the machine without any problem.

<h4>Downlaoding and set up the Vulnable machine<b>NOT RECOMMEND TO FOLLOW MY STEP SINCE THE MR ROBOT I AM USING HAVE VIRUS IN IT ACCORDING TO WINDOWS DEFENDER</b></h4>

![download](https://github.com/Shecklock/HACKING_LAB/assets/84926502/3e2c1900-eedc-46e9-a52b-e27657aee158)![images](https://github.com/Shecklock/HACKING_LAB/assets/84926502/fb2395ff-83e6-4ba2-8d99-a2a789d303d7)
![download](https://github.com/Shecklock/HACKING_LAB/assets/84926502/c927a39d-f626-4bc4-b04f-684b8cd34b02)<br>

![download](https://github.com/Shecklock/HACKING_LAB/assets/84926502/48b4ad84-3703-4171-ba92-3338d8ef096c)
Here are the [Vulnhub](https://www.vulnhub.com/), a platform that provides materials allowing anyone to gain practical hands-on experience with digital security, computer applications and network administration, etc<br>

I am using the Mr robot, and my nightmare started here.
<b>THIS IS THE MOST ANNOYING PART OF THOS PROJECT SINCE IT SAID HAVE VIRUS - A LOVELY TROJAN:Win32/Casdet!rfn</b>
Windows defender said it have virus Trojan:Win32/Casdet!rfn, which is a threat software belonging to the Trojan horse family. It is a  computer virus  designed to damage systems by creating security vulnerabilities and stealing sensitive data.

I have thought a long time, take the risk or not? And i remember i have another old laptop in my house.
So I decided to downlad the file in my backup laptop so it won't affect my main computer, and check for the file hash (MD5/SHA1)to ensure the file integrity from vulnhub using powershell command "get-filehash -algorithm MD5 ./Downloads/mrRobot.ova"<br>
![螢幕擷取畫面 (298)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/b1fc8b1f-4a9e-481a-892b-c5a6770a399e)

<b>I THOUGHT I HAVE TO USE THE COMMAND PROMT, AND THE ONLY THING I GOT BACK IS NO SUCH COMMAND FROM CMD. TURNS OUT I HAVE TO USE POWERSHELL</b>(It took me a week for finding my computer+and the hash checking)
The result is it si the same in the vulnhub as showed below:

![螢幕擷取畫面 (300)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/9988cad7-13de-4158-8aff-7ee6aa916334)<br>

So i took the risk and transfer my file to my main computer, and import it into the Virtual box. After the importation, I delete the file immediately.

![螢幕擷取畫面 (302)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/af90c79e-7d6e-4183-b650-68dc8e42e447)

<h4>Connecting two machine together and isolate them</h4>

The final part is connecting the two machine together and isolate them so when i am playing with it, i won't accidentally hacked into other things, so this can become a safe environment for praticing my skils.<br>
TO do this, simply change the network setting for both VM attachment from NAT(or whatever ir origanlly linked) to internal network<br> 
<b>NOTE: ensure both of them are connecting to the same internal network</b>
![螢幕擷取畫面 (303)](https://github.com/Shecklock/HACKING_LAB/assets/84926502/accf8f1c-0c5a-4365-a034-1428adbbdeb5)

But they don't have a DHCP server, which in other words means they won't have ip address when they boot up, so we have to create one<br>
