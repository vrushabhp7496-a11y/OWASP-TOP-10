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


### 3. A07 Authentication Failures : 
- This vulnerability happens when application fails to trust that user is legitmate or valid user.
- This happens because of the following reasons
   1. Weak and guessable passwords.
   2. Lack OF Multifactor authentication
   3. Session fixation

---

### How attacker exploit it 
1. Brute force attack : Automating login request by using wordlist to guess the right password
2. Credential stuffing : Assume you loging some website and set some password but that website itself got hacked then attacker can use your password on another site,or can use it on your      own account
3. Session hijacking : Stealing a valid session cookie (usually via XSS or MITM) and using it to impersonate the user without needing the password.

---
- To overcome this following standards must be follwed.
  1. Use strong password policy
  2. use MFA
  3. Rate limiting to avoid brute force.
  4. Sessions regeneration.
 
---

### Lets see tryhackme rooms lab to better understand this vulnerability :

---

<img width="566" height="559" alt="Screenshot 2026-05-04 234211" src="https://github.com/user-attachments/assets/90fd696e-892e-4a12-9171-6ff2df5e49d1" />

Here i created account with name of "aDMIN"

---

<img width="551" height="485" alt="Screenshot 2026-05-04 234226" src="https://github.com/user-attachments/assets/0b14ce76-4189-4648-83ed-5043fa7b92d2" />

Then i tried to login using account name "admin"

---

<img width="818" height="695" alt="Screenshot 2026-05-04 234241" src="https://github.com/user-attachments/assets/3e9d3c10-139c-459c-a7f5-fb32cf8f2e62" />

And i succed to get in that account beacsue server failed to authenticate the legitmate user between "aDMIN" and  "admin".

---

### 4. A05 Security Misconfiguration : 
- This happens because when software or website or application is designed with software flaws,exposed services,or weak policies.
- Thes are not code bugs but these are the misconfiguration enviroment in where software is designed.
- This is the critical vulnerability as it can lead to massive data breach,complete system exposure,attacker can  get privilage.


---

### Common reasons are : 
- Weak credentials or passwords
- Outdated softwares.
- Design with known vulnerabilities.
- Misconfigured configrations.
- Verbose error messaages exploiting system informations.


---

### Preventions :
- Apply strong password policy.
- Regular software update.
- Design with proper known vulnerabilitis to avoid them.
- Proper configuration
- Error messages kept user friendly.


 ---


### 5. A02 Cryptographic Failures :
- It means that encryption for data in transit or data in store is weak or falsly configured or totally not well applied.
- This is very critical vulnerability as it can expose data to attacker or hacker in plain text form.
- This may can lead in password exposure,data breach or even gaining unauthorised access to system by using password exposed.


  ---

  ### Common reasons :
- Using old hashing like MD% and SHA 1
- No encryption.
- Weak SSL TLS Certificate or self signed certificates.
- Hardcoded credentials. ( Writing password in Source code which are easily visible)

---

### Preventions : 
- Use strong algorithms
- Use encryptions
- Store password in enviromental variables.
- Update TLS.

#### Below i have added some screenshots from tryhackmes room : 


---

<img width="1231" height="652" alt="Screenshot 2026-05-10 172424" src="https://github.com/user-attachments/assets/bd4ab8a7-0cc5-4432-ae66-2bcc3eeecdad" />


---

<img width="1193" height="572" alt="Screenshot 2026-05-10 172613" src="https://github.com/user-attachments/assets/bb230957-d215-4015-92c2-027872a157fb" />


---

<img width="327" height="78" alt="Screenshot 2026-05-10 172625" src="https://github.com/user-attachments/assets/89435e1c-cb16-42eb-91f3-4af7eec8d3c7" />

---

<img width="1547" height="565" alt="Screenshot 2026-05-10 173104" src="https://github.com/user-attachments/assets/11acdd1f-3c9b-44b9-8f74-293f66c945e3" />


---

### 6. A04 Insecure Design :
- This happen when a flawed logic is built in system,website or application without reviwing it.
- Some security measures are skipped.
- With AI design developers relay too much on AI generated code trusting that these are reliable are flawless this measure causing poor architectural pattern.

---

### Some common design flaws are :
- User ID in URL
- No rate limiting on OTP.
- SQL injection at login.

---

### Prevention : 
- Threat MOdeling ( See where Hacker can attack)
- User privilage (Only grant needed access)
- Always keep scure default setting like password policy.
- Design system assuming breach.


---


### A06 Vulnerable and outdated componants :
- This happens when application depend on componant which is compromised,improperly configured,outdated.
- This is not source code vulnerability but this may can weaakness where vendor is itself compromised to any one of weakness listed above.
- Attacker exploit this to inject malicious code bypass security or steal sensitive data.


---

### Common reasons :
- Using untrusted componants or libraries.
- Auto installing software updates without configuring
- Over relay on third party without auditing it.
- Lack of modeling for vulnerabilities in dependencies after deployement.

---

### Preventions :
- Alwys prefer trusted and verified componants and libreries.
- Always configure and check software upadte for bugs.
- Always do auditing of third party vendors and componants before taking service.
- Regular vulnerability checking.7



  
   




 






      

  


