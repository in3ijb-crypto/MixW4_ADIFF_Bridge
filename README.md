[ReadMe.txt](https://github.com/user-attachments/files/28348028/ReadMe.txt)
text======================================================================
     MIXW4 TO LOG4OM REAL-TIME ADIF BRIDGE
======================================================================
Version: 1.0
Author: Mauro, IN3IJB
License: Free for amateur radio use
======================================================================

This lightweight utility acts as a real-time bridge between MixW4 
and Log4OM. Since MixW4 stores QSOs in a local SQLite (.db3) database 
and lacks an automatic real-time ADIF export, this tool monitors the 
database and instantly feeds new QSOs into Log4OM via its ADIF Monitor.


PREREQUISITES
----------------------------------------------------------------------
* MixW4 installed and configured.
* Log4OM (v2) installed and configured.


HOW IT WORKS
----------------------------------------------------------------------
1. The app runs in the background and monitors your MixW4 .db3 file.
2. When a new QSO is saved in MixW4, the app detects it instantly.
3. The app extracts the data, converts it to ADIF, and writes it to 
   a dedicated .adi file.
4. Log4OM's ADIF Monitor scans this file and imports the QSO automatically.


STEP-BY-STEP CONFIGURATION
----------------------------------------------------------------------
STEP 1: Find your MixW4 Database
* The database file is usually named "multipan.db3" (or your callsign.db3).
* Common locations in Windows:
  Option A: C:\Users\[YourUsername]\AppData\Roaming\MixW Software\MixW4\
  (Note: "AppData" is a hidden folder by default in Windows)
  Option B: C:\Program Files\MixW4\ or C:\Program Files (x86)\MixW4\
* Tip: If you cannot find it, open MixW4, go to its file/profile settings 
  to see exactly where your active log database is stored.

STEP 2: Configure this Bridge Utility
* Launch MixW4_ADIFF_Bridge.exe.
* The application automatically finds your user profile and creates 
  a secure, dedicated folder in your AppData directory.
* It will immediately generate the output ADIF file in that secure location.

STEP 3: Configure Log4OM
* Open Log4OM and go to: Settings -> Configuration.
* Navigate to "Inbound Settings" -> "ADIF Monitor".
* Check the box to "Enable ADIF Monitor".
* Set the "Monitor Folder" path to:
  C:\Users\[YourUsername]\AppData\Roaming\MixW4_to_Log4OM_Bridge\
* Save and apply the settings.


TESTING THE CONNECTION
----------------------------------------------------------------------
1. Keep both Log4OM and this Bridge utility running.
2. Log a dummy or real QSO inside MixW4.
3. Check the Bridge console window to confirm the QSO was detected.
4. Check your Log4OM recent QSOs list; the contact should appear 
   within a few seconds.


FEEDBACK & BUG REPORTS
----------------------------------------------------------------------
This software is provided "as-is" to help the amateur radio community. 
If you find any bugs, missing ADIF fields, or have suggestions for 
improvements, please reach out on the community thread.

73 de IN3IJB
======================================================================
