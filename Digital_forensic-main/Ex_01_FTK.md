# Ex.No.1 FTK IMAGER  
# AIM 
   Document a forensically sound acquisition of a storage device/folder and (optionally) system memory using FTK Imager.
FTK Imager: A Forensic Imaging Tool Overview. Acquiring Volatile Memory (RAM) Using FTK Imager

# Description
FTK Imager is a forensic acquisition tool developed by AccessData that allows investigators to create exact copies of digital media without altering the original evidence. It can capture data from hard drives, USB devices, and memory, generate hash values for integrity verification, and preview files and recover deleted data

# Steps to Capture RAM Using FTK Imager
### 1. Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the FTK Imager icon and select **Run as administrator**.
<br>
<br>
<img width="1110" height="832" alt="Screenshot 2025-10-31 011313" src="https://github.com/user-attachments/assets/5b57fa47-ad27-4fda-b94a-8f50b478c8b2" />



<br>
<br>

### 2. Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory...** from the dropdown list.
  <br>
<br>

<img width="1919" height="1079" alt="1" src="https://github.com/user-attachments/assets/e5ab9ee3-23ef-4528-8903-e243705c85f5" />

<br>
<br>

### 3. Configure Destination
A dialog box will appear where you configure where and how the memory will be saved.

- **Destination Path:**  
  Click **Browse** to select a folder on an **external drive** (not the system drive).  

- **Destination Filename:**  
  You can keep the default `memdump.mem` or assign a more descriptive name.

- **Optional: Include pagefile.sys**  
  Check this box to capture `pagefile.sys`, which is virtual memory stored on the disk.  
  > Note: This may increase capture size and duration, but can contain valuable artifacts.

- **Optional: Create AD1 file**  
  Saves the memory dump in an AccessData-specific container file.  
  > Generally not necessary if using tools like **Volatility** for analysis.



<br>
<br>

<img width="1919" height="1079" alt="2" src="https://github.com/user-attachments/assets/422c5d3a-d6b6-4e13-9598-549e68305008" />

 
<br>
<br>

### 4. Start Capture
- Click the **Capture Memory** button to begin acquisition.
<br>
<br>



<img width="1919" height="1079" alt="3" src="https://github.com/user-attachments/assets/06ad22f4-84d0-460f-bab5-2aae52d43e7e" />

<br>
<br>

### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
- 
<img width="1919" height="1079" alt="3" src="https://github.com/user-attachments/assets/68dd4a0e-630e-4cfa-9beb-5b4d3627bd0f" />
- 
---
<br>
<br>

## Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager


### 1. Start the Process
- In FTK Imager, go to the top menu bar: **File → Create Disk Image...**.

<br>
<br>
<img width="1919" height="1016" alt="Screenshot 2025-08-30 113433" src="https://github.com/user-attachments/assets/5a453707-3a07-4d3f-8b58-7745cac9ef5d" />


<br>
<br>

### 2. Select Source Evidence Type
A window will appear asking you to choose the source type:

- **Physical Drive:** Images the entire disk, including all partitions, unallocated space, and the Master Boot Record (MBR).  
- **Logical Drive:** Images a specific partition (e.g., C: drive).  
- **Image File:** Converts or copies an existing image file.  
- **Contents of a Folder:** Creates an image of a specific folder only.  

> **Tip:** For full forensic imaging, select **Physical Drive**.
<br>

<img width="1089" height="735" alt="image" src="https://github.com/user-attachments/assets/57410fe3-2963-4196-82a3-1f0a9ef10804" />
<br>
<br>

### 3. Select the Source Drive
- From the dropdown, choose the physical drive to image (connected via **write-blocker**).  
- Click **Finish**.
 <br>
<br>
<img width="1089" height="731" src="https://github.com/user-attachments/assets/2dc222b0-372b-472d-95c7-d88f763e8d06" />

<br>
<br>

### 4. Configure the Image Destination
- Click **Add...** in the "Create Image" window to define the image **format** and **destination**.
  <br>
<br>
<p align="center">
<img width="1084" height="735" alt="image" src="https://github.com/user-attachments/assets/0bb36fb7-b1e4-4c29-8fc8-c4682d6e8785" />
<br>

#### Options:

- **Image Type:**  
  - **E01 (EnCase Format):** Recommended; includes compression, metadata, and error-checking.  
  - **Raw (DD):** Bit-for-bit copy with no extra features.
<br>
<br>
<p align="center">
<img width="1091" height="735" alt="image" src="https://github.com/user-attachments/assets/11927a3a-6d4b-4017-be40-1cbbfc38800a" />

</p>
<br>
<br>

- **Fill in Evidence Item Information:**  
  - Enter case details, examiner name, and description.  
  - This information is stored in the image metadata (important for documentation).
 <p align="center">
<img width="1919" height="1079" alt="6" src="https://github.com/user-attachments/assets/b3d253aa-ddad-417f-a11c-6cf6f69b708b" />

</p>
<br>
<br>

- **Choose Destination Folder:**  
  - Must be a different drive from the source.  
  - Name the image file (e.g., `Case001_SuspectHDD`).  

- **Image Fragment Size:**  
  - Set a value to split the image into multiple parts.  
  - Set to `0` for a single image file.
  <br>
  <br>
  
<p align="center">
<img width="1919" height="1079" alt="7" src="https://github.com/user-attachments/assets/76bfbeaa-a188-4d69-bffd-941753d6adbd" />
</p>
<br>
<br>


### 5. Start the Imaging Process
- Click **Finish** to return to the "Create Image" screen.  
- **Check "Verify images after they are created"** to calculate hash values and ensure integrity.  
- Click **Start**.
  <br>
  <br>
  <p align="center">
<img width="1919" height="1079" alt="8" src="https://github.com/user-attachments/assets/3228c063-a78c-45cd-8789-6cc1e7608b6f" />

<img width="1919" height="1079" alt="9" src="https://github.com/user-attachments/assets/9538bd4f-c6ea-48b3-b46f-21d2eacd7979" />

</p>
<br>
<br>

### 6. Completion and Hash Verification
- The imaging process may take time depending on the drive size.  
- After completion, FTK Imager verifies the hashes automatically.  
- A final window shows **MD5** and **SHA1** hashes for both the source drive and image.  
- Matching hashes confirm the forensic image’s integrity.

## Result
The acquisition process using FTK Imager was successfully carried out on the selected evidence source. A forensic image in E01 format was created and verified using multiple hashing algorithms (MD5, SHA1, and SHA256). The computed values matched the expected results, confirming the integrity of the image.
