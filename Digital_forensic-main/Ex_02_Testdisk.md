#  Ex.No.2    TestDisk: Open-Source Data Recovery Tool

## Aim :
To use TestDisk step by step to recover a missing partition and repair a corrupted one.



## 🛠️ Installation
Linux (Debian/Ubuntu): sudo apt-get install testdisk

macOS (Homebrew): brew install testdisk

Windows: Download the executable from the official CGSecurity website.

## Procedure

### 1. Create a Log File
- Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

- Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.
<br>
<br>

<img width="973" height="505" alt="Screenshot 2025-09-01 205558" src="https://github.com/user-attachments/assets/b39f0972-0fb4-4566-97c5-ad0a742ebe8d" />

</p>
<br>
<br>

### 2. Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<br>
<br>

<img width="974" height="506" alt="Screenshot 2025-09-01 205647" src="https://github.com/user-attachments/assets/60bdd5ee-0522-4a66-88e6-15ebcd8e9f81" />

</p>
<br>
<br>

- Select [Proceed] to move to the next step.

### 3. Choose the Partition Table Type
- TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

- The default value is usually correct. Confirm the selection by pressing Enter.
<br>
<br>
<img width="974" height="506" alt="Screenshot 2025-09-01 205725" src="https://github.com/user-attachments/assets/1a8d3f00-93f2-47e2-aa3e-4098d75b3277" />
</p>
<br>
<br>

### 4. Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
<br>
<br>
<img width="974" height="505" alt="Screenshot 2025-09-01 205746" src="https://github.com/user-attachments/assets/40f14ab2-7fde-4f4f-bed8-1b5021e42e1e" />
</p>
<br>
<br>

- This will display the current partition table and check for errors or missing partitions.

### 5. Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search].

<br>
<br>
<img width="1042" height="687" alt="Screenshot 2025-09-01 214306" src="https://github.com/user-attachments/assets/4cd1a716-cafe-48f6-bd76-52b04256fd1d" />

</p>
<br>
<br>

- Select it and press Enter to scan the drive for lost partitions.

- Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

- Press q to return to the search results.

  ### 6. Perform a Deeper Search
- If the Quick Search fails to find your lost partitions, select [Deeper Search].

-<br>
<br>
<img width="1034" height="693" alt="Screenshot 2025-09-01 214332" src="https://github.com/user-attachments/assets/7cd5bc6d-c467-4b65-85f6-39443433c353" />

</p>
<br>
<br>

- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

- Again, use p to preview files and confirm if a found partition is the one you are looking for.

### 7. Modify Partition Status
- After finding the correct partitions, use the Left/Right arrow keys to set their status.

- Use **Left/Right arrow keys** to change status:  
  - **P**: Primary  
  - ***:** Bootable  
  - **L**: Logical  
  - **D**: Deleted

    <br>
<br>
<img width="1722" height="1015" alt="Screenshot 2025-09-01 214358" src="https://github.com/user-attachments/assets/020a79c5-40f9-4783-9f92-f455a9d571b2" />

</p>
<br>
<br>

- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).

### 9. Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Navigate to the folder containing your desired files.

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.

### 10. Exit and Restart
- Once your task is complete, select [Quit] to exit the program.

- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.

- # Result
- Using the TestDisk tool, the lost partition was successfully detected and restored 🔄. The recovered files and directories were made accessible again without data modification 📂, and the integrity of the restored data was verified ✅. This demonstrates the tool’s effectiveness in partition recovery and data forensics.
