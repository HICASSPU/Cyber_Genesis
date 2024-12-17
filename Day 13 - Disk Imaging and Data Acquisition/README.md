# **Cyber Genesis - Day 13: Disk Imaging and Data Acquisition** 🛠️🔍  

Welcome to **Day 13 of the Cyber Genesis series!** 🚀  
Today, we focus on one of the most critical stages of digital forensics: **Disk Imaging and Data Acquisition**. This step ensures evidence is preserved in a forensically sound manner, maintaining its integrity for analysis and legal admissibility.

---

## **What is Disk Imaging and Data Acquisition?**

**Disk Imaging** is the process of creating a **bit-by-bit copy** of a digital storage device (e.g., hard drives, SSDs, USBs). This ensures that the original evidence remains untouched while investigators analyze the duplicate.  

**Data Acquisition** refers to securely collecting data from storage devices, ensuring no tampering or loss of integrity.

---

## **Why is Disk Imaging Important?**

1. **Preservation of Evidence**  
   - Ensures the original evidence remains unaltered.  
   - The forensic image serves as the “working copy” for analysis.

2. **Integrity Verification**  
   - Hash values (MD5/SHA1/SHA256) are generated to verify the image’s integrity.

3. **Legal Admissibility**  
   - Forensic imaging maintains a clear chain-of-custody, making evidence admissible in court.

4. **Repeatability**  
   - Investigators can replicate the analysis using identical copies of the image.

---

## **Types of Disk Images**

1. **Raw Image Format (.dd/.img)**  
   - A bit-for-bit copy of the original disk.  
   - Tool: `dd` (Linux).  

2. **E01 (Expert Witness Format)**  
   - Compresses the disk image and stores metadata like hash values and acquisition logs.  
   - Tool: FTK Imager.  

3. **AFF (Advanced Forensic Format)**  
   - Open-source format that allows for compression and encryption.  

---

## **Tools for Disk Imaging and Data Acquisition**

### **1. FTK Imager** (GUI Tool)  
**Description**: FTK Imager is a user-friendly tool for creating forensic images and verifying their integrity.  
- **Features**:  
   - Supports raw (`.dd`) and E01 formats.  
   - Preview files without altering them.  
   - Generate MD5/SHA hash values for verification.  

**Steps to Use FTK Imager**:  
1. Download and install **FTK Imager**.  
2. Connect the target device (e.g., hard drive or USB).  
3. Open FTK Imager and select:  
   - **File > Create Disk Image**.  
4. Choose the source (physical drive) and output format (e.g., E01).  
5. Verify integrity using generated hash values.  

---

### **2. `dd` Command (Linux CLI)**  
**Description**: `dd` is a powerful command-line utility for creating raw disk images.  

**Syntax**:  
```bash
dd if=/dev/sdX of=/path/to/image.dd bs=4M status=progress
```
- **if**: Input file (source drive).  
- **of**: Output file (destination for image).  
- **bs**: Block size (recommended: 4M for faster imaging).  
- **status=progress**: Displays progress while creating the image.  

**Example**:  
```bash
dd if=/dev/sdb of=/home/user/forensic_image.dd bs=4M status=progress
```

**Verify Image Integrity**:  
Use `md5sum` or `sha256sum` to generate and compare hashes:  
```bash
md5sum /path/to/image.dd
```

---

### **3. iMazing** (For Mobile Data Extraction)  
**Description**: iMazing is a tool for securely extracting data from iOS devices (iPhones/iPads).  

**Features**:  
- Recover messages, call logs, photos, and app data.  
- Useful for mobile forensics and iOS data acquisition.  

**Resource**:  
- [Read the iMazing Blog Guide](https://bytebloggerbase.com/main/6746138ef8f9136ee7864762).  

---

### **4. Guymager** (Linux GUI Tool)  
**Description**: Guymager is an open-source disk imaging tool with a graphical interface.  
- **Features**:  
   - Supports `.dd` and `.E01` formats.  
   - Generates hash values for integrity verification.  

**Installation on Linux**:  
```bash
sudo apt-get install guymager
```

---

## **Best Practices for Disk Imaging**

1. **Use Write-Blockers**  
   - Write-blockers ensure no modifications are made to the target device during imaging.

2. **Generate Hash Values**  
   - Calculate hash values before and after imaging to ensure integrity.  

3. **Use Proper Storage**  
   - Store forensic images on dedicated external storage or servers.

4. **Document Chain of Custody**  
   - Maintain detailed logs of who handled the evidence, when, and how.

---

## **Practical Exercise**

### **Scenario:**  
A USB drive is suspected to contain malicious or stolen data.  

#### **Steps to Investigate**:  
1. **Create a Forensic Image**  
   - Use **FTK Imager** or the `dd` command to create an image of the USB.  
   - Example (`dd`):  
     ```bash
     dd if=/dev/sdb of=/home/user/usb_image.dd bs=4M status=progress
     ```

2. **Verify Integrity**  
   - Generate and compare MD5 or SHA256 hash values.  
   - Example:  
     ```bash
     md5sum /home/user/usb_image.dd
     ```

3. **Analyze the Image**  
   - Use tools like **Autopsy** or **Sleuth Kit** to search for deleted files, metadata, or suspicious data.

---

## **Resources for Day 13**

### **Official Resources**  
- [FTK Imager Download and Guide](https://www.exterro.com/digital-forensics-software/ftk-imager)  
- [iMazing Blog Guide](https://bytebloggerbase.com/main/6746138ef8f9136ee7864762)  

### **Interactive Labs**  
- **TryHackMe**: [Disk Imaging Room](https://tryhackme.com/r/room/autopsy2ze0)  
- **Cyber Defenders**: Disk Imaging Challenges.

---

## **Ethics and Legal Considerations**

1. **Integrity**: Always use tools that preserve evidence without modification.  
2. **Privacy**: Only analyze data when authorized to do so.  
3. **Chain of Custody**: Maintain detailed logs to ensure evidence is admissible in court.  

---

## **Created by:**

**Varad Mene**

---

## **Contributing**  
Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
