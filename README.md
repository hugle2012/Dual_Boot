# Dual_Boot
How did I safely quarantine my OS.

🧪 How I Safely Quarantined My Windows OS (via Dual Boot with VHDX)
💡 This is just one method to dual-boot your computer using a VHDX (Virtual Hard Disk).
If you know a faster or cleaner way, feel free to message me at: Facebook


🔧 Step 1: Download the Windows ISO
Download the official ISO file from Microsoft:
👉 https://go.microsoft.com/fwlink/?linkid=2156295

After downloading, mount the ISO. You should see something like:
![image](https://github.com/user-attachments/assets/573dde7e-716e-4372-87d3-331595ba6b0b)

💽 Step 2: Create a VHDX File
Right-click the Start Menu and select Disk Management

Go to Action → Create VHD

✔️ Recommended options:

Format: VHDX

Type: Dynamically expanding

Size: At least 50GB

Location: Somewhere on a different partition (e.g., D:)

🖇️ Step 3: Mount and Apply the Windows Image
Find the version index using PowerShell (run as admin):

powershell
Copy
Edit
dism /Get-WimInfo /WimFile:E:\sources\install.esd
🔍 This will list all versions in the ISO.
I recommend using the same version as your current OS to avoid activation issues.

Apply the Windows image to the VHDX (replace E: and D: as needed):
Dism /Apply-Image /ImageFile:E:\sources\install.esd /Index:6 /ApplyDir:D:\
🚀 Step 4: Add to Boot Menu
After applying, run:
bcdboot D:\Windows
📌 This will add your new Windows OS to the bootloader menu.

✅ Done!
You can now reboot your PC and select your "quarantined" Windows OS to run apps or tools without affecting your main system.


