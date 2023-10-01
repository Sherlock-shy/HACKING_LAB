<h1>Virtual machine hacking lab</h1> 
Making a lab for practicing any cyber skills

inspire by: https://www.youtube.com/watch?v=mvsiuLzpx2E

<h2>Environment used</h2>

- Oracle VM Virtual Box
- Vulnhub Mr. Robot(Not recommended, reason will be state out later)

<h2>Steps go through </h2>

step 1 download and install virtual box adn virtual box extension manager
step 2 download kali linu and the vulnerable machine
step 3 connect them together 
step 4 Make their network isolated
step 5 Start hacking(As this is just set up, the walk through will be write in another repositories)

<h2>Walk through</h2>

Windows defender said it have virus Trojan:Win32/Casdet!rfn)
i decided to downlad the file in my backup laptop so it won't affect my main computer, and check for the file hash (MD5/SHA1)to ensure the file integrity from vulnhub using powershell command "get-filehash -algorithm MD5 ./Downloads/mrRobot.ova"
