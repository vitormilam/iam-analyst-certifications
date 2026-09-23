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



## MFA (Multi Factor Authentication) 

- It's all about providing 2 differents kinds of proof during authentication and this can be a mix between various factors.

Something you KNOW: Password, PIN. 
+
Something you HAVE: Phone, Security Key.
+
Something you ARE: Fingerprint, face.

- To be considered a MFA, it need at leat to be a mix of 2 or more of this.


## Conditional Access

- We allow or deny access to resources by considering certain signals.
- It's a Microsoft EntraID feature that controls access to applications and resources based on specific conditions.

What Conditional Access Checks
- User: Who is signing in?
- Location: Where are they signing in from?
- Device: Is the device trusted/compliant?
- Application: What app is being accessed?
- Risk: Is the sign-in suspicious?

Conditional Access does not equal MFA
- Conditional Access decides when security controls are applied.
- MFA is one of the controls that Conditional Access can enforce.


## Entra Roles and Azure Role-Based Access (RBAC)

EntraID Roles
- They govern access and permissions in our Entra directory.
- Also, in M365.


Azure Role-Based Access (RBAC)
- RBAC controls the access and permissions for Azure Resources.
- Such as Virtual Machines, Azure functions, storage.

- Both focus on the same thing, giving people authorization to interact with resources.
- But for different Domains.
- EntraID focus on the entraid tenant and M365.
- RBAC focus on Azure.


## EntraID Protection

- Microsoft Entra ID Protection is a security feature that helps detect, investigate, and respond to identity-based risks.

What does it do?
- Entra ID Protection uses Microsoft security intelligence to detect risks such as: 
  - Stolen Credentials.
  - Password spray attacks.
  - Sign-ins from unusual locations.
  - Impossible Travel (login from two distant locations in a short time).
  - Anonymous IP addresses (VPN/Tor).

| Feature             | Purpose                                         |
| ------------------- | ----------------------------------------------- |
| Conditional Access  | Controls access based on conditions             |
| Entra ID Protection | Detects identity risks and compromised accounts |


## EntraID PIM (Priveleged Identity Management)

- In many organizations, users may have powerful roles such as: Global Administrator, Security Administrator, User Administrator.
- If these permissions are always active, a compromised account could cause significant damage.
- So, PIM gives admin access only when it's needed, and only for a limited time.

- Microsoft Entra ID Privileged Identity Management (PIM) is a service that enables just-in-time, time-limited, and audited access to privileged roles,
reducing the risks associated with permanent administrator permissions.


############################################################################################################################33


# DOMAIN 3 (It's all about the security services that azure provides)


## Azure DDoS Protection

- Azure DDoS Protection is a service that protects Azure applications and resources from Distributed Denial-of-Service (DDoS) attacks.
- We can simply enable DDoS protection for our public facing resources and for our Azure VNets.

What's a DDoS Attack?
- A DDoS attack happens when attackers send a massive amount of traffic to a website or application to make it unavailable.



## Azure Firewall

- It's a cloud-native network security service that controls and filters network traffic going in and out of Azure resources.
- It has Network rules, Application rules, NAT rules.


## Azure Web Application Firewall (WAF)

- Is a security device that protects web applications from common web-based attacks.
- It hepls block attacks such as:
 - SQL injection.
 - Cross-Site Scripting (XSS)
 - Bot attacks
 - Malicious web requests.


- A normal firewall focuses on network traffic.
- A Web Application Firewall (WAF) focus on HTTP/HTTPS web traffic and analyzes requests sent to websites.



## Network Security Groups (NSGs)

- Network Security Groups are used to allow or deny network traffic to Azure Resources.
- Think of an NSG as : "A set of firewall rules for Azure Networks Resources".

What's Network Segmentation?
- Network segmentation means dividing a network into smaller, isolated sections to improve security.
- Each segment can have different security rules.
- This helps prevent attackers from moving freely within the network.



## Azure Bastion

- It`s a service that allows you to securely connect to Azure Virtual Machines (VMs) using RDP (Windows) or SSH (Linux) directly through the Azure Portal without exposing the VM to the public internet.

Key Benefits
- Secure VM Access.
- No public IP Required.
- Reduced Attack Surface.



## Azure Key Vault (Parei em 01:08:03)

