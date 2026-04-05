# Phase 1: Building a Windows Domain Environment

## Overview

For this phase of my home lab, I focused on building a basic Windows domain environment from scratch. The goal was to simulate a real-world enterprise setup where systems are centrally managed and users authenticate through Active Directory. 
This environment serves as a virtual playground where I can experiment with new concepts, learn tools, and simulate both real-world attacks and day-to-day administrative tasks such as password resets, user management, and Group Policy configuration. Ultimately, this gives me a hands-on way to build and manage my own small-scale enterprise environment. 

---

## What I Built

I set up a small network consisting of:

- Windows Server 2022 (Domain Controller)
- Windows 11 (Client Machine)
- Kali Linux (for future attack simulation)

The Windows Server was promoted to a Domain Controller for the domain:
corp.local

<a href="https://github.com/user-attachments/assets/25802bac-fc53-4674-b6aa-fdd23415e538">
  <img src="https://github.com/user-attachments/assets/25802bac-fc53-4674-b6aa-fdd23415e538" width="700">
</a>

This included setting up:
- Active Directory Domain Services (AD DS)
- DNS for domain name resolution

## Challenges I Ran Into

- Initial domain controller promotion failed due to weak/blank Administrator password requirements
- Resolved by setting a compliant local Administrator password and rerunning prerequisites

---

## User & Identity Setup

After configuring the domain, I created user accounts inside Active Directory to simulate a real environment:

- ashton.user (standard user)
- it.admin (administrative-style account)

<img width="624" height="351" alt="Picture2" src="https://github.com/user-attachments/assets/78d8bb14-7da3-4c21-9cab-7926672a36eb" />

This allowed me to test authentication and user management within the domain.

---

## Domain Join & Authentication

I then joined the Windows 11 client machine to the domain and verified that domain authentication was working correctly.

<img width="624" height="351" alt="Picture3" src="https://github.com/user-attachments/assets/de584ae9-4f9a-445d-8c26-d537c45d35f0" />

To confirm this, I logged in as a domain user and used:
whoami

Which returned:
corp/ashton.user

<img width="624" height="351" alt="Picture4" src="https://github.com/user-attachments/assets/aea51b78-1f6a-422a-8ff6-37d9683eaaac" />

## Key Takeaways
- Active Directory relies heavily on DNS — incorrect DNS settings will break domain functionality
- Account context (who you are logged in as) matters more than expected
- Building a domain environment requires both configuration and validation

---

## Outcome

By the end of this phase, I successfully:

- Built a functioning Active Directory domain
- Created and managed user accounts
- Joined a client machine to the domain
- Verified domain authentication

This environment will serve as the foundation for future phases, including monitoring, detection, and attack simulation!
