UCSFilesManager
===============

Author: Julien Leprette


Hey there! 

I'm Julien, a French composer and professional sound designer based in France. 
Specializing in sound design for video games, I've collaborated with various games studios, 
honing my skills in creating immersive soundscapes, recording and mixing foleys, and seamlessly integrating 
sounds into game environments. My passion lies in solo game development and tool creation, 
as well as crafting simple scripts in Reaper. Always eager for new projects and collaborations, 
I'm committed to bringing creativity and expertise to every endeavor. Let's create something together!

https://julienleprette.com

UCSFilesManager Overview
========================

UCSFilesManager is a software tool designed for sound designers and sound design studios to organize their sound libraries 
following the Universal Category System (UCS) standard. This tool was conceived by myself to streamline the process of 
sorting and renaming sound files based on predefined categories and keywords.

Installation :
==============

Simply place the "UCSFilesManager-main" folder in the desired location (e.g., the Programs folder),
extract the UCS(folders).zip archive (it's UCS hierarchy empty folders, the destination path) 
and launch UCSFilesManager.exe. You can create a shortcut on your desktop.


Paths Setup Instructions
========================

1. Source Directory:
   - The source directory should be the folder containing the sound assets or the sound library you want to organize.
   - The software can search for sound files within the subdirectories of this source directory.

2. Destination Directory:
   - The destination directory is the folder named `UCS` and placed in the root of the project.
   - This directory can be moved to a drive (such as using the Google Drive desktop app or NAS Server) to directly upload the sounds to the cloud 
     or local server.

Using UCSFilesManager
=====================

1. Launching the Application:
   - Open the application and you will see fields to enter paths for the source directory and destination directory.
   - These directories are saved for the next time (history.txt).

2. Renaming and Sorting Files (Move Files):
   - The software reads the `data.txt` file to get the sorting information.
   - It reads keywords from the files in the keywords directory to match and only rename the non-UCS sound files.
   - The sound files are renamed using the selected format (Custom or Basic)
   - Files with the UCS format are just moved without renaming.
   - Files are moved to the appropriate folder and subfolder in the destination directory based on the prefix.
   - If you want to confirm the new names and move files with only one prefix possibility, just check "Show prefix selection for single option". 
     (If this option is not checked, the file is renamed and moved automatically without a confirmation box.)

3. Prefix Selection Window:
   - If multiple prefixes match a file, the software prompts the user to select the appropriate prefix.
   - The selection window shows the original file name and the destination folder and subfolder for each prefix option.
   - Here you can also ignore the current file, listen to the current file, delete the current file, select the correct prefix from the complete 
     list and edit the wildcards/format.

4. "Only Rename" Button:
   - Added a new button to perform only the renaming operation without moving the files. This is useful if you want to review the renamed files 
     before organizing them.

5. Adding custom Keywords:
   - To customize keyword matching, add or edit keywords in the `.txt` good CatId files.
     For example, if you often work with voice actors, you can easily add their names to the list of words in the "VOX..." files. 
     These CatIDs will then be suggested if your actors' names are present in the non-UCS file names.
   - Ensure keywords are separated by commas for proper recognition by the software.
     WARNING! The plural is not automatic, you must therefore rewrite the keyword a second time in the plural (example: footstep and footsteps).

6. Logs:
   - The software maintains a log of all operations performed, including renamed files, moved files paths, and user choices. 
   - Paths in the logs are clickable, allowing you to open them directly.

UCS Basic Mode / UCS Wildcards mode
===================================


UCS Basic mode :

The basic mode allows you to enter 3 additional nomenclature data besides the CatID: the microphone used, the sound designer (creator ID), 
and the studio name. The options entered will be saved for future use in history.txt. The format will be :

 CatID_(original file name)_Mictype_SoundDesigner_StudioName. 

Feel free to change the logic as you wish.

Example with the move files logic :

- Original File Name:
  Compressed_Air.wav

- Keywords File (`keywords/AIRBlow.txt`):
  Aerate, Aerosol, Air, Compressed, Balloon...
 (The program finds the appropriate keywords file; we have 2 keywords that match!)

- Data File (`data.txt`):
  AIR,BLOW,AIRBlow
  (The program finds the folder path based on data.txt information.)

- Renamed File:
  AIRBlow_Compressed_Air_Mic_Author_Studio.wav

- Moved To:
  UCS/AIR/BLOW/




UCS Custom mode :

The custom mode allows you to personalize your nomenclature after the CatID. You can add wildcards to automatically 
retrieve certain information in the desired order. You can save the presets by checking the associated checkbox or by 
editing the wildcards.txt file at the root of the project. Here is the list of currently implemented wildcards:

$filename (current file name)
$date     (actual date DD_MM_YYY)
$year     (actual year YYYY)
$isrc     (random 8 character for unique identifier code)

If you have a file named "car crash.wav" november 3 2024,

If you type : $filename_Hello_$date_$isrc

your file are rename : DESTRCrsh_car crash_Hello_03_11_2024_Gj5lm7U2


Contact
=======

For any issues or further customization, feel free to contact me: https://julienleprette.com
