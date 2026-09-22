# SC-900 Microsoft Security, Compliance, and Identity Fundamentals Study Cram v2

Link: https://www.youtube.com/watch?v=79HpgR_TYlM

## DOMAIN 1

## Shared Responsability Model

On-Premises
 - Data: YOU
 - Accounts and Identities: YOU
 - Devices: YOU 
 - Applications: YOU
 - Operating System: YOU
 - Network Controls: YOU
 - Physical (host, network, datacenter): YOU

IaaS (Infrastructure as a Service)
 - Data: YOU
 - Accounts and Identities: YOU
 - Devices: YOU
 - Applications: YOU
 - Operating System: YOU
 - Network Controls: SHARED
 - Physical (host, network, datacenter): MICROSOFT

PaaS (Plataform as a Service)
 - Data: YOU
 - Accounts and Identities: YOU
 - Devices: YOU
 - Applications: SHARED
 - Operating System: MICROSOFT
 - Network Controls: MICROSOFT
 - Physical (host, network, datacenter): MICROSOFT

SaaS (Software as a Service)
 - Data: YOU
 - Accounts and Identities: YOU
 - Devices: YOU
 - Applications: SHARED
 - Operating System: MICROSOFT
 - Network Controls: MICROSOFT
 - Physical (host, network, datacenter): MICROSOFT



## Defense in Depth

LAYER 01 - Physical Security
- All physical control on datacenters.

LAYER 02 - Identity & Access
- Controls who has access to what kinds of information in our company.

LAYER 03 - Perimeter
- It's related to everything that is internet facing, such as web application firewalls.

LAYER 04 - Network
- Our intranet.

LAYER 05 - Compute
- On-premises servers, virtual machines on cloud like azure/aws.

LAYER 06 - Application
- The various application that both, employee and users, can interact.

LAYER 07 - Data
- 



## CIA Triad

- Confidentiality: Only the right people can read it.
- Integrity: Nobody tampered with it.
- Availability: It's there when you need it.



## Zero Trust in Azure

1° Verify Explicitly
 - Authenticate & authorize on every signal -- who, what device, where, how risky.

2° Use least privilege
 - Just enough access, just in time and no more.

3° Assume breach
 - Operate as if the attacker is already inside.



## Encryption

- Encryption is all about making sure that even if you have a breach, the data that the adversaries and the attackers have access is encrypted.
- So, even if they get their hands on the data, they cannot read.


### There 2 types of encryption: SYMMETRIC and ASYMMETRIC

### Symetric Encryption
 - One shared key locks AND unlocks.
 - FAST but both sides need the same secret and sharing it safely is the hard part.

### Asymetric Encryption
 - The public key encrypts the data and the private key decrypts the data.
 - A public/private pair - what one locks, only the other one opens.
 - Hand your public key to the whole world but only your private key opens what's sent to you.


## Hashing

- It's a one-way street, usually called a trap door function.
- If you hash a information, you can't un-hash it.
- Hash function always produce the output for the same input.



## GRC (Governance, Risk & Compliance)

- Governance: 
 - The rules.
 - Policies and proccesses that keep the organization in line.

- Risk:
 - Spot what could go wrong, how bad it would be, and decide what to do about it.

- Compliance:
 - Meet the external bar - laws, regulations, standards like GDPR or ISO 27001.


## Authentication and Authorization

What's Authentication?
 - It's basically about proving who you are to the company by provading a password, one-time code, face/biometric.

What's Authorization?
 - What you are allowed to do, for example, which apps, which data and which actions.

- Authentication always happens before authorization.


############################################################################################################################33


# DOMAIN 2

## Microsoft Entra ID

- Entra ID is Microsoft Cloud Identity Provider.
- It's basically the front door for everything you use in the Microsoft Cloud.

- Identity Provider: Authenticate & SSO to every app.
- Conditional Access: Grant access on real-time signals.
- ID Protection: Detect Risky users and Sign-ins.
- PIM: Just-in-time admin access.
- Hybrid Identity: Bridge on-prem AD to the cloud.


### Identity Types:

- User: A human -- employee or guest.
- Service Principal: An identity for an app.
- Managed Identity: App identity Azure manages -- no secrets to handle.
- Device: The machine, not the person.
- AgentID: AI agents get their own identity.

What's Hybrid identity?
- It allows the user to sync his/her identity between different enviroments.
- To do this, we use ENTRA CONNECT in azure.

- Entra Connect allows the user to sync on-premises accounts from on-premises up to the cloud into Entra ID.


### Entrad ID Authentication Metodos

- Passwordless: Authenticator approval, windows hello, FIDO2 key.  (STRONGEST)
- One-time Codes: Authenticator code, OATH token, SMS/phone call.   (STRONGER)
- Password Alone: just a password.  (WEAKEST)
- SSPR: Self-service password reset - no help-desk ticket.
- Password Protection: bans weak passwords - smart lockout.



## MFA (Multi Factor Authentication) PAREI EM 41:03