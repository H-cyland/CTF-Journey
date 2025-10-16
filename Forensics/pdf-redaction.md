# Challange : Hidden PDF Flag 
**Category:** Forensics 
**Platform:** University of Warwick Cyber Security society
**Date:** 10/10/2025 ~ 12/10/2025

## 1. Chanllenge Description 
The PDF appeared to have redacted text, but hidden data remained in the file. 
<img width="559" height="635" alt="image" src="https://github.com/user-attachments/assets/71728071-7a29-454a-803c-ad0eac807218" />

## 2. My Approach 
1. Opened the file in **HxD Editor** and **Notepad++** to inspect both raw and readable content. 
2. Searched for readable text segments that might align with visible words in the PDF, assuming some text could be hidden or replaced. 
3. Checked nearby areas in the file for recognizable patterns or metadata clues.
4. No readable or hidden data was found at this stage.

## 3. Write-up Reference
After my initial attemtps, I referred to a write-up from the same challenge.
It explainedthat the PDF used **incremental updates**, meaning new data was appended to the end od the file instead of replacing the old content.
This helped me understand the concept of '%%EOF' signatures and why there were multiple and how deleting data after the first one restores the original version. 

## 4. What I Learned
- The structure of a PDF consists of **objects** and **cross-reference table (xref)**
- Each revision in a PDF ends with its own '%%EOF' signature.
- Understanding these signatures helps identify hidden or appended data in forensic analysis.

## 5. Next Time 
When I face a similar PDF challenge next time, I will start by locating the **%%EOF** signature and analyzing the sturcture around it. 
