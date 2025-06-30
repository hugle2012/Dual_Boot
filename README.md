# Dual_Boot
How did I safely quarantine my OS.

Firstly, I must tell that is just one of ways that you can dual-boot your computer, if you has any other faster or cleaner way, please tell me via: https://www.facebook.com/lil.haize

The first step, you need to have an iso media creation tool installed in your disk already, here's mine:
![image](https://github.com/user-attachments/assets/573dde7e-716e-4372-87d3-331595ba6b0b)
You can download the iso file from microsoft official page here -> https://go.microsoft.com/fwlink/?linkid=2156295
Do the following step and you would get the windows disc file like this
![image](https://github.com/user-attachments/assets/05572343-db1c-4464-a54e-22bad0581d2f)
Next, you must get a vhdx(Virtual Hard Disk) file on your computer, here's how it has done:
1. Right click on your windows logo and choose "Disk Management":
![image](https://github.com/user-attachments/assets/06b8725b-3cf1-463c-8fbc-b058f64bbe52)
2. Select Action->Create VHD
![image](https://github.com/user-attachments/assets/f49077ab-136b-4a40-a9ee-4a5132189684)
3. You should check the following selection for a dynamic sized disk, of course it is for future usage. Then browse the folder you want to store it:
![image](https://github.com/user-attachments/assets/14e3fd3d-f1e5-4edf-92ec-dad29ab3c063)
![image](https://github.com/user-attachments/assets/97fc6803-c605-4031-93fc-a4495419cb84)
   Here's the size of your vhd, I prefer >50Gb:
![image](https://github.com/user-attachments/assets/13c6997c-61a1-4d3e-8ae3-26029aab417a)

Secondly, you have to get your windows11 file attaches to your vhdx file, here's how you do it:
1. Get the versions of the ISO file that you have mounted, using powershell(REMEMBER TO RUN AS ADMINISTRATOR), dism /Get-WimInfo /WimFile:E:\sources\install.esd
 , it can contain several version at once, but I recommend you to install the version that IS your current windows version for official activation.
![image](https://github.com/user-attachments/assets/a968823f-b4fe-4d57-bc42-c6aba9969c6e)
2. Use the following prompt to start to attach iso into your vhdx file:  Dism /Apply-Image /ImageFile:E:\sources\install.esd /Index:6 /ApplyDir:D:\    (Replace "E" and "D" with your disk, respectively it is MOUNTDISK(E:), VHDX(D:))
![image](https://github.com/user-attachments/assets/7377a647-3e3d-4ec3-9463-f92c3f3227d1)
3. Last step, paste this command to powershell: bcdboot D:\Windows
![image](https://github.com/user-attachments/assets/c7543aa2-1125-45a8-b47f-c8be2b2051fb)

Now, your dual-boot windows is ready to go when you restart your PC ;)


