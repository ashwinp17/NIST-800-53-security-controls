# NIST 800-53 Password Policy Implementation Lab

## Project Overview

This lab focused on implementing and validating password security controls on a Windows Server hosted in Microsoft Azure.

I used the Local Group Policy Editor to configure password requirements, applied the updated policy, and tested the controls using a dedicated test account. The goal was to understand how NIST 800-53 security requirements can be translated into technical Windows configurations and then validated to confirm that the controls are functioning as intended.

The lab primarily mapped to:

- **AC-2 – Account Management**
- **IA-5 – Authenticator Management**

---

## Technologies Used

- Microsoft Azure
- Windows Server
- Local Group Policy Editor
- Windows Command Prompt
- Group Policy
- NIST SP 800-53
- Remote Desktop Protocol (RDP)

---

## Lab Objectives

The objectives of this lab were to:

- Configure stronger password requirements using Group Policy
- Enforce password complexity
- Prevent immediate password reuse
- Configure password expiration
- Apply updated Group Policy settings
- Test whether the password policy was actually enforced
- Connect technical Windows configurations to NIST 800-53 controls

---

# Password Policy Configuration

I navigated to:

`Computer Configuration > Windows Settings > Security Settings > Account Policies > Password Policy`

and configured the following security settings:

| Security Setting | Configuration |
|---|---|
| Minimum password length | 14 characters |
| Password complexity | Enabled |
| Password history | 5 passwords remembered |
| Maximum password age | 90 days |

---

## 1. Minimum Password Length

I configured the minimum password length to require passwords containing at least **14 characters**.

This helps reduce the effectiveness of password guessing and brute-force attacks by increasing password length.

![Minimum Password Length](nist-password-minimum-length-14.png)

---

## 2. Password Complexity

I enabled the Windows setting:

**Password must meet complexity requirements**

This requires passwords to meet stronger complexity requirements instead of allowing simple passwords.

![Password Complexity](nist-password-complexity-enabled.png)

---

## 3. Password History

I configured Windows to remember the previous **5 passwords**.

This prevents users from immediately reusing recently used passwords.

![Password History](nist-password-history-5.png)

---

## 4. Maximum Password Age

I configured the maximum password age to **90 days**.

This setting controls how long a password can remain active before Windows requires it to be changed.

![Maximum Password Age](nist-password-max-age-90.png)

---

# Applying the Policy

After configuring the password settings, I opened an elevated Command Prompt and ran:

```cmd
gpupdate /force
