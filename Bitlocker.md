
###description:

BitLocker is a full volume encryption feature included with Microsoft Windows versions starting with Windows Vista. It is designed to protect data by providing encryption for entire volumes. By default, it uses the AES encryption algorithm in cipher block chaining or XTS mode with a 128-bit or 256-bit key.

### managed by:

Helpdesk and EUC

### TROUBLESHOOTING:

﻿[How to Setup / Troubleshoot Bitlocker](https://app.getguru.com/card/c58rzRAi/How-to-Setup-Troubleshoot-Bitlocker)﻿

**Before proceeding, be sure you have access to the machine's Bitlocker recovery key in the event one is needed during computer reboot.** If you have the Intune access, the key can be found within the Intune admin portal here [https://entra.microsoft.com/#home](https://entra.microsoft.com/#home) Next, locate Devices > All Devices and search for the computer name. Select the device found, then Bitlocker keys to find the latest recovery key. **Follow these steps if Bitlocker app is not resolving the "prompting for recovery key on reboot" issue:**

Run this command in a DOS admin mode window and restart the computer:

_**manage-bde -protectors c: -disable -rebootcount 1**_

This just disables Bitlocker and does not allow it to re-enable after so many reboots (in this case just one).

_**1 = keep it disabled until the device reboots once 2 = keep it disabled until the device reboots twice x = keep it disabled until the device reboots x number of times (replace x with a number) 0 = keep it disabled forever**_

Once it comes back up and find recovery key, perform the following in a DOS admin mode window:

_**manage-bde.exe –protectors –disable C:**_ then _**manage-bde.exe –protectors –enable C:**_

Then reboot the computer for the test. The machine should no longer prompt for a recovery key upon reboots.

### Copy pastas:

Link cards with generic responses or 'copy pastas' that can be sent to users. Like Oracle password reset instructions.

### LAST VERIFIED BY:

Reed, 4/16/2024

Cristobal, 6/8/2023