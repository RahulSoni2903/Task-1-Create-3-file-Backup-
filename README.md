# 📁 Task-1-Create-3-file-Backup (SSIS Project)

This project uses a single input file (or multiple files available in one source folder) and automatically copies the files to a second folder, then compresses the copied files into a ZIP archive and stores the ZIP file in a third folder.  
It demonstrates a simple and professional file-handling workflow for copy and archive operations using SSIS. ⚙️📦

---

## 🖼 Source File

Here IT is File 1 Is Source File

<img width="813" height="245" alt="Source" src="https://github.com/user-attachments/assets/b2ebe3c4-3799-4b39-9065-29d4224f3ccb" />

---

## 🧩 SSIS Package Flow Structure

2nd image is structure of FLOW

<img width="1086" height="576" alt="Structure (2)" src="https://github.com/user-attachments/assets/0f9cae74-ed43-4491-96bc-00bc16f1668c" />

---

## ⚙️ File System Task – Create Destination Directory

3rd image is configuration of File System Task.

In this task we create a directory and use a variable named **DestinationLocation** which contains:
## C:\Users\Aum S\Desktop\Inkey Internship\SSIS Extra\File Create\Destination


This means the Destination folder is created at the above location.  
Here we use a 🔁 **ForEach Loop** to iterate a location and retrieve available files.

<img width="750" height="717" alt="Screenshot (843)" src="https://github.com/user-attachments/assets/1c9dd2b8-ffdf-43af-9c80-a95daf53cf9b" />

---

## 🔁 ForEach Loop Configuration

Now this is configuration of the ForEach Loop.

The ForEach Loop is used to iterate through all files present in the Source folder and pass the fully qualified file path to a variable.

<img width="786" height="697" alt="Screenshot (844)" src="https://github.com/user-attachments/assets/b2fc61cb-73da-4a41-b01c-63ed649aa42a" />

---

## 📂 Destination Folder (After ForEach Loop)

After running the ForEach Loop, 3 files from the Source are copied and stored at the Destination location. ✅

<img width="857" height="246" alt="Destination" src="https://github.com/user-attachments/assets/20810941-d43e-4f26-a3bb-824f8445e394" />

---

## 📁 Create New Folder for ZIP Output

Now after the ForEach Loop, we again use a File System Task to create a new folder.

We pass a variable named **CreateDirectory** which contains:

 C:\Users\Aum S\Desktop\Inkey Internship\SSIS Extra\File Create\NewFolder


This folder is used to store the final ZIP file. 🗜️
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b3eeb782-13d9-4fa5-ac1b-6e51c7f165f1" />

<img width="1122" height="244" alt="NewFolder" src="https://github.com/user-attachments/assets/be7e8878-e8e4-4438-b4c5-8b0811f6ba99" />

---

## 🗂 File System Task – Create New Folder Configuration

<img width="749" height="704" alt="Screenshot (845)" src="https://github.com/user-attachments/assets/56ec5709-e94d-490e-97ff-6c119560b175" />

---

## 🗜 Zip Copied Files Using Execute Process Task

After creating the NewFolder, we zip the copied files (not the folder).  
For this, we use an 🛠️ **Execute Process Task**.

The basic requirement is a ZIP executable file.

Executable path used on my system:
## C:\Users\Aum S\Desktop\Inkey Internship\SSIS\03-02-2026\File Transfer(Copy)\7za.exe


Arguments used in Execute Process Task:
## a -tzip "C:\Users\Aum S\Desktop\Inkey Internship\SSIS Extra\File Create\NewFolder\MyZip.zip" "C:\Users\Aum S\Desktop\Inkey Internship\SSIS Extra\File Create\Destination\*"


⚠️ Important Note  
The `*` at the end of the destination path is mandatory.  
It ensures that only the files are zipped, not the entire folder.

---

## ✅ Conclusion

This project automates file backup by copying source files to a destination folder and compressing them into a ZIP archive using SSIS.  
It provides a clean, reliable and reusable workflow for file copy and archive operations using ForEach Loop and system tasks.
