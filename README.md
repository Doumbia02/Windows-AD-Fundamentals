**<h1># Windows-AD-Fundamentals</h1>**

**<h2>Task 1: Understand Active Directory Architecture</h2>**

**<h4>🎯 Goal</h4>**
Understand what Active Directory is and how it enables centralized identity and access management.

**<h4>🔍 Explanation</h4>**
Active Directory (AD) is a directory service used by organizations to centrally manage:

Users
Computers
Groups
Permissions
Authentication
Key AD components:

Domain → Logical boundary for users and computers
Domain Controller (DC) → Server that stores and enforces AD data
Forest → Top-level AD structure containing one or more domains
LDAP → Protocol used to query AD
Kerberos → Default authentication protocol

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Log in to your Windows Server.

2️⃣ Open Server Manager → Review installed roles.

3️⃣ Confirm Active Directory Domain Services (AD DS) role is installed.

**<h2>Task 2: Explore Active Directory Users & Computers (ADUC)</h2>**

**<h4>🎯 Goal</h4>**
Learn how users, groups, and computers are organized in Active Directory.

**<h4>🔍 Explanation</h4>**
Active Directory Users and Computers (ADUC) is the primary tool for managing AD objects.

Objects include:

User accounts
Computer accounts
Security groups
Organizational Units (OUs)

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Open:

dsa.msc

2️⃣ Explore default containers:

Users

Computers

Domain Controllers

3️⃣ Identify built-in groups like:

Domain Admins

Domain Users

**<h2>Task 3: Create and Manage User Accounts</h2>**

**<h4>🎯 Goal</h4>**
Create and manage domain user accounts.

🔍 Explanation
In AD, user accounts represent real people or services and are used for authentication and authorization.

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ In ADUC, create a new user:

Username: ad_user1

Set a password

2️⃣ Enable / disable the account.

3️⃣ Reset the user’s password.

4️⃣ Log in to a domain-joined client using this user.

**<h2>Task 4: Understand Groups and Group Scope</h2>**

**<h4>🎯 Goal</h4>**
Learn how group-based access control works in Active Directory.

**<h4>🔍 Explanation</h4>**
Groups simplify permission management.

Group types:

Security Groups → Used for permissions
Distribution Groups → Email only
Group scopes:

Domain Local
Global
Universal
**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Create a Security Group named IT_Support.

2️⃣ Add ad_user1 to the group.

3️⃣ Assign folder access using group permissions.

**<h2>Task 5: Organizational Units (OU) & Delegation</h2>**

**<h4>🎯 Goal</h4>**
Understand how enterprises logically organize AD objects.

**<h4>🔍 Explanation</h4>**
Organizational Units (OUs) are containers used to:

Organize users and computers
Apply Group Policies
Delegate administrative control
**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Create OUs:

HR

IT

Finance

2️⃣ Move users into appropriate OUs.

3️⃣ Delegate limited permissions on an OU.

**<h2>Task 6: Domain Authentication & Kerberos Basics</h2>**

**<h4>🎯 Goal</h4>**
Understand how users authenticate in Active Directory environments.

**<h4>🔍 Explanation</h4>**
Active Directory uses Kerberos for authentication.

High-level flow:

User logs in
DC verifies credentials
Ticket Granting Ticket (TGT) is issued
User accesses services using tickets
This process is frequently targeted in attacks (Pass-the-Ticket, Kerberoasting).

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Log in as a domain user.

2️⃣ Open Command Prompt:

klist

3️⃣ Observe Kerberos tickets.

**<h2>Task 7: Group Policy Fundamentals</h2>**

**<h4>🎯 Goal</h4>**
Understand how Group Policy enforces security and configuration.

**<h4>🔍 Explanation</h4>**
Group Policy Objects (GPOs) allow administrators to:

Enforce password policies
Restrict applications
Configure security settings

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Open:

gpmc.msc

2️⃣ Create a new GPO:

Enforce password complexity

3️⃣ Link the GPO to an OU.

4️⃣ Run on client:

gpupdate /force

**<h2>Task 8: AD Security Logs & Monitoring</h2>**

**<h4>🎯 Goal</h4>**
Identify AD-related security events for SOC monitoring.

**<h4>🔍 Explanation</h4>**
Active Directory generates critical security logs.

Important Event IDs:

4624 → Successful login
4625 → Failed login
4768 → Kerberos TGT request
4769 → Service ticket request

**<h4>🛠️ Hands-On Exercise</h4>**
1️⃣ Open:

eventvwr.msc

2️⃣ Navigate to Security Logs.

3️⃣ Filter Event ID 4624 and 4768.

4️⃣ Identify:

Username
Logon type
Source system
