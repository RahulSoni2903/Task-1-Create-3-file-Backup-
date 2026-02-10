# 📁 Task-1-Create-3-file-Backup (SSIS Project)

This project uses a single input file (or multiple files available in one source folder) and automatically copies the files to a second folder, then compresses the copied files into a ZIP archive and stores the ZIP file in a third folder.  
It demonstrates a simple file-handling workflow for copy and archive operations using SSIS.

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
C:\Users\Aum S\Desktop\Inkey Internship\SSIS Extra\File Create\Destination


This means the Destination folder is created at the above location.  
Here we use a **ForEach Loop** to iterate a location and retrieve available files.

<img width="750" height="717" alt="Screenshot (843)" src="https://github.com/user-attachments/assets/1c9dd2b8-ffdf-43af-9c80-a95daf53cf9b" />

---

## 🔁 ForEach Loop Configuration

Now this is configuration of the ForEach Loop.

The ForEach Loop is used to iterate through all files present in the Source folder and pass the fully qualified file path to a variable.

<img width="786" height="697" alt="Screenshot (844)" src="https://github.com/user-attachments/assets/b2fc61cb-73da-4a41-b01c-63ed649aa42a" />

---

## 📂 Destination Folder (After ForEach Loop)

After running the ForEach Loop, 3 files from the Source are copied and stored at the Destination location.

<img width="857" height="246" alt="Destination" src="https://github.com/user-attachments/assets/20810941-d43e-4f26-a3bb-824f8445e394" />

---

## 📁 Create New Folder for ZIP Output

Now after the ForEach Loop, we again use a File System Task to create a new folder.

We pass a variable named **CreateDirectory** which contains:

