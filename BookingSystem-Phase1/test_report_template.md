# 1️⃣ Introduction

**Tester(s):**  
- Name: NELZY Charles-André

**Purpose:**  
- penetration and functionality testing on the application's registration page

**Scope:**  
- Tested components: website page, MyPostGreSQL database
- Exclusions:  
- Test approach: Gray-box

**Test environment & dates:**  
- Start:  15:37 18th Nov
- End:  16:48 18th Nov
- Test environment details (OS, runtime, DB, browsers):

**Assumptions & constraints:**  
- e.g., credentials provided, limited time, etc.

---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  

**Overall risk level:** High
**Top 5 immediate actions:**  
1.  Use variables for the input and then use it for your commands so that its content can't be run as commands.
2.  look for common ways of writing special characters involved in paths like / or \ and make sure to strip them of the input.
3.  Apply encryption server-side (a one-way incryption is commonly used for passwords) and then store the encrypted version
4.  Apply conditions on the input such as minimum of characters, presence of special characters, numbers
5.  Apply conditions on the Birthdate input to have minimal age necessary to use the booking service

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings 


| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | SQL Injection in registration | Input field allows `' OR '1'='1` `' AND '1'='1` injection |<img width="924" height="389" alt="image" src="https://github.com/user-attachments/assets/4359732f-b31e-4fb6-a393-578ebf839470" />
| F-02 | 🔴 High | Path Traversel | username can be made with special characters using their ASCII format | <img width="840" height="130" alt="image" src="https://github.com/user-attachments/assets/9dfeddfc-79df-4a8b-a871-1b12cce21670" />
| F-04 | 🟠 Medium | Database format | Information are clear in the database, no encryption of info | <img width="840" height="130" alt="image" src="https://github.com/user-attachments/assets/c7a2edb7-7bd0-4267-aeac-dad612f56cb4" />
| F-05 | 🟡 Low | Weak password policy | Accepts passwords like "12345" | <img width="595" height="133" alt="image" src="https://github.com/user-attachments/assets/9292c45a-13e8-4985-8af3-782406ef8fc1" />
| F-05 | 🟡 Low | Birthdate input| Accepts birthdate in the future | <img width="595" height="133" alt="image" src="https://github.com/user-attachments/assets/7c5ee838-38e9-46ae-bbba-8415a369930c" />


# 5️⃣ OWASP ZAP Test Report (Attachment)

**Purpose:**  
- Attach or link your OWASP ZAP scan results (Markdown format preferred).

---

**Instructions (CMD version):**
1. Run OWASP ZAP baseline scan:  
   ```bash
   zap-baseline.py -t https://example.com -r zap_report_round1.html -J zap_report.json
   ```
2. Export results to markdown:  
   ```bash
   zap-cli report -o zap_report_round1.md -f markdown
   ```
3. Save the report as `zap_report_round1.md` and link it below.

---
> [!NOTE]
> 📁 **Attach full report:** → `check itslearning` → **Add a link here**

---
