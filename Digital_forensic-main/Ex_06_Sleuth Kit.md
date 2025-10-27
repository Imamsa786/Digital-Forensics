# Ex.No.06 Sleuth Kit 

# Aim:
To study and use of Sleuth Kit for analyzing disk images and recovering digital evidence through command-line forensic tools.
# Description:
The Sleuth Kit (TSK) is an open-source suite of command-line tools used in digital forensics. It allows investigators to analyze disk images, examine file systems, and recover deleted or hidden files. TSK plays a key role in extracting and preserving digital evidence for investigation.

#  Tools Required
- The Sleuth Kit (TSK)  
- Autopsy  
- Linux/Windows Operating System  
- Terminal or Command Prompt

- # Procedure
## step 1. Open Terminal
   Launch the Terminal Linux or Command Prompt for Windows on your system.

   
### 2: Prepare Disk Image (Evidence Collection)
Before analysis, a **bit-by-bit copy** (disk image) of the storage device evidence is required.

### 3. Create Disk Image: 
   - Use a forensic tool like **FTK Imager** or the Linux `dd` command to create a bit-by-bit copy of the target drive.  
   - Ensure the image format is supported by TSK

### 4. Download Sample Files:  
   - For this exercise, download the following sample disk image files:  
     - `4Dell Latitude CPi.E01`  
     - `4Dell Latitude CPi.E02`

---

## Step 2: Mount the Disk Image (Optional)
Mounting the image simplifies browsing and analysis.

### 1. Mount Image:  
   - Use **OSFMount** (on Windows) or `mount` (on Linux) to mount the image as a virtual drive.  
   - This allows easy viewing of the file system, though all forensic analysis must still be done on the image copy to preserve evidence integrity.

---

## Step 3: Analyze the File System
Use Sleuth Kit commands to examine the disk image and locate digital evidence.

### 1. Navigate to the Sleuth Kit Directory:  
     ```bash
     cd "C:\Program Files\SleuthKit\bin"
### 2 Identify File System Information with fsstat:

    bash
      fsstat image.E01 > filesystem_info.txt
Purpose: Displays detailed information about the file system, including type, sector size, and volume layout.

### 3 List Partitions using mmls:
      bash
      mmls image.E01 > partitions.txt
Purpose: Lists the partitions present within the image file.

### 4 List Files Recursively using fls:

    bash
    fls -r image.E01 > file_list.txt
Purpose: Lists all files and directories recursively with their inode numbers.

### 5 Recover Deleted Files using icat:

    bash
    icat image.E01 <inode_number> > recovered_file.txt
Purpose: Recovers a specific deleted file using its inode number obtained from fls.

## Step 4: Analyze Metadata
## Use TSK tools to extract detailed file metadata for forensic insight.

### 1 View File Metadata with istat:

    bash
    istat image.E01 <inode_number> > metadata_info.txt
Purpose: Displays file size, allocation status, and MAC times (Modified, Accessed, Changed).

## Step 5: Timeline Analysis (Optional)
## Reconstruct user activity by creating a forensic timeline.

### 1 Generate Body File using fls:

    bash
    fls -m / -r image.E01 > body.txt
Purpose: Creates a body file containing MAC times and file paths.

### 2 Generate Timeline with mactime:

    bash
    mactime -b body.txt > timeline.txt
Purpose: Creates a chronological timeline of file activities (modifications, access, and changes).

## Step 6: Generate Forensic Report
### 1 Document and compile the findings.

Collect Output Files:
filesystem_info.txt
partitions.txt
file_list.txt
metadata_info.txt

### 2 Prepare Report:

Summarize key findings, such as recovered files, file metadata, and timeline insights.

Include screenshots, hash values, and command outputs for verification.

## Step 7: Preserve and Store Evidence
## Maintain evidence integrity and ensure compliance with chain of custody procedures.

### 1 Archive Evidence:

Securely archive both the original disk image and analysis outputs.

Generate MD5 or SHA-256 hash values for verification.

### 2 Store Securely:

Keep the archived data in a secure, access-controlled environment.

Maintain logs for all handling and analysis actions.

## Result
The Sleuth Kit experiment successfully analyzed the provided .E01 disk image.
Partitions and file system structures were identified using mmls and fsstat.
Deleted files were recovered with icat, metadata was extracted using istat, and a detailed activity timeline was generated using mactime.
All outputs were securely archived to maintain evidence integrity.

## Conclusion
The Sleuth Kit (TSK) provides powerful command-line tools for detailed forensic analysis of disk images.
It enables investigators to recover deleted data, extract file system metadata, and reconstruct user activity timelines, ensuring accurate and reliable digital evidence examination.
