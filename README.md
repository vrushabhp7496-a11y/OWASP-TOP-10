# **Welcome back to my new project**
---
## 😈 OWASP TOP 10

---

- Before knowing the vulnerabilities in OWASP top 10 lets know what is OWASP acutually is
---

# -OWASP : Open Web Application Security Project
- OWASP is the organization which works on most critical vulnerabilities on web appliaction and websites.
- They release this list of top 10 vulnerabiloities in every 2-3 years.
- I have listed OWASP Top 10 vulnerabilities below in table we will see one by one using tryhackme labs.
- ---

| Rank | Category | Description |
| :--- | :--- | :--- |
| **A01** | Broken Access Control | Users can access resources they shouldn't (IDOR, privilege escalation) |
| **A02** | Cryptographic Failures | Sensitive data exposed due to weak or missing encryption |
| **A03** | Injection | SQLi, NoSQLi, OS Command Injection, LDAP Injection |
| **A04** | Insecure Design | Architectural flaws that cannot be fixed with code alone |
| **A05** | Security Misconfiguration | Default passwords, verbose errors, missing security headers |
| **A06** | Vulnerable & Outdated Components | Using libraries or frameworks with known CVEs |
| **A07** | Identification & Authentication Failures | Weak session management, credential stuffing |
| **A08** | Software & Data Integrity Failures | Race conditions, insecure CI/CD pipelines |
| **A09** | Security Logging & Monitoring Failures | No audit trail, delaying breach detection |
| **A10** | Server-Side Request Forgery (SSRF) | Abusing server functionality to make internal requests | 

---

### The IAAA is nothing but the process of identifying the users and their actions on webapplication or on website.The process is explained below .It is crucial to the IAAA to undertstand OWASP top 10

### -Before diving in OWASP top 10 lets see what is IAAA
- IAAA:
1. Identity
2. Authentication
3. Authorization
4. Accountability

---

1. Identity : It is the unique account that represent unique person or service to whom its belong.
2. Authentication : Proving that identity by means of password or biometric identity.
3. Authorization : This defines the permisissions which are alocated for that account to do
4. Accountability : Recording and alerting monitoring that who did what,where,and when.

---

### Lets see OWASP Top 10 one by one 

---

## 1. A01 BROKEN ACCESS CONTROL :
- This vulnerability happens when server dosent properly manage who can access what,or in simple words one user can see account info of another user by changing user id only.
- This shows Horizontal user escalation that means same user but seeing another users info.
- IDOR (INSECURE DIRECT OBJECT REFRENCE )is the example of Broken access control.
- Lets see this by Tryhackme Lab,i have added the screenshot below.

  ---

  <img width="868" height="800" alt="Screenshot 2026-05-04 222637" src="https://github.com/user-attachments/assets/f48c98e5-084b-421b-adad-08aaea089161" />

  ---

  Here i simply changed the user account number and i saw another users account detail,see the 2 screenshots below.

  --

  <img width="899" height="810" alt="Screenshot 2026-05-04 222654" src="https://github.com/user-attachments/assets/4e88a831-61bc-4cce-ba01-26f3792581ef" />

  ---

  <img width="900" height="820" alt="Screenshot 2026-05-04 222720" src="https://github.com/user-attachments/assets/0f2189fb-331c-4dfd-8dbe-5444b564e07f" />


  ---

  ### 2. A09 Logging and alerting failures :
- When dosent record or alert on security event related events this cause Logging and aleerting failure.
- Consider if an attacker is doing Brute force,Privilage escalation,but you are unknown of this attacks beacause application failed to detect them or handaled this event very softly.
- This is the most critical vulnerability because of the following points
    1. The attacks are undetected
    2. Attacker can tamper system untill its gets detected
    3. Compliance gets failed
    4. Forensics is very critical in this carse.

  ---

   - To overcome this following standard must be followed
      1. Send log to every SIEM tool like firewall,server,application
      2. Create automated alerts for ex 5 failure logins are detected
      3. Create logs not only for errors but also for suspicious activity.

  ---

  ### Lets see screenshots below from tryhackme room

  ---

  -- In the following screenshot the application shows the attacker tried to do brute force attack and succed to that and gained access to admin account

  ---

  <img width="853" height="360" alt="Screenshot 2026-05-04 224520" src="https://github.com/user-attachments/assets/78e48439-85dc-43af-8f73-22cc62362e90" />


  ---


  <img width="862" height="408" alt="Screenshot 2026-05-04 224541" src="https://github.com/user-attachments/assets/6a899b34-754c-40af-896f-a602ec5a5d15" />


---




      

  


