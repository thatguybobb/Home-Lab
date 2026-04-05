# Phase 1: Building a Windows Domain Environment

## Overview

For this phase of my home lab, I focused on building a basic Windows domain environment from scratch. The goal was to simulate a real-world enterprise setup where systems are centrally managed and users authenticate through Active Directory.

---

## What I Built

I configured a small network consisting of:

- Windows Server 2022 (Domain Controller)
- Windows 11 (Client Machine)
- Kali Linux (for future attack simulation)

The Windows Server was promoted to a Domain Controller for the domain:
corp.local

This included setting up:
- Active Directory Domain Services (AD DS)
- DNS for domain name resolution

---

## User & Identity Setup

After configuring the domain, I created user accounts inside Active Directory to simulate a real environment:

- ashton.user (standard user)
- it.admin (administrative-style account)

This allowed me to test authentication and user management within the domain.

---

## Domain Join & Authentication

I then joined the Windows 11 client machine to the domain and verified that domain authentication was working correctly.

To confirm this, I logged in as a domain user and used:
whoami

Which returned:
corp/ashton.user

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

This environment will serve as the foundation for future phases, including monitoring, detection, and attack simulation.
