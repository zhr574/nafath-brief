Version: NAFATH-V1
Track: Cybersecurity 
# Overview
The six layers of a national single sign-on service are interdependent because it allows citizens to log in to government services just once.The exchange of identity and 
access is defined by software protocols such as OpenID Connect and OAuth 2.0. Permissions must be kept to a minimum because the majority of citizens utilize mobile apps
for single sign-on services. While cybersecurity provides phishing-resistant authentication, networking safeguards the path, for instance, using encrypted DNS. While AI
aids in login detection, it also poses hazards. The guidelines for managing people' identifying data at all levels are established under data protection law. A flaw in 
any one layer has the potential to erode confidence in the national single sign-on service as a whole.

# Software
•	An authorization mechanism called OAuth 2.0 allows an application to obtain restricted access to a resource on a user's behalf using access tokens without disclosing
the user's password. It makes no mention of how you authenticate the user. On top of OAuth 2.0, OpenID Connect adds an identity layer with the ID token, which informs the 
application about the user's identity and method of authentication. In other words, OAuth provides an answer to the query "what can this app access?" while OpenID "Who is
this user?" is answered by Connect.
Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html

# AI
I believe that a model that flags logins may miss attackers (false negatives) or mistakenly block law-abiding citizens (false positives). I think it's important to measure
the model's correctness rather than assume it. If people, devices, or areas are underrepresented in training data, the model can be biased. Attackers can change to go 
around the model. Through its Govern Map, Measure, and Manage functions—which assign accountability, document context, test performance and bias, and continually monitor 
and respond, including review and appeals—NIST's AI RMF tackles these issues.
Resource: NIST AI Risk Management Framework 1.0 - https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf

# Mobile
Android divides permissions into different categories. Permissions are typically granted by Android upon installation. Android makes runtime permission requests as well.
When a feature requires Android runtime permissions, those permissions are asked. The user can grant on Android. Refuse every request. If access is denied, Android
anticipates that the Android app will continue to function. Only what is actually required, like camera access for ID scanning, should be requested by Android login apps,
and Android should provide an explanation.
Resource: Android Developers, Permissions overview - https://developer.android.com/guide/topics/permissions/overview

# Networking
RFC 8484 describes DNS over HTTPS, which transmits DNS requests within HTTPS connections. This implies that while the queries are moving, other users along the network
path cannot view or modify them. Between the client and the DoH server, this aids in protecting the data. It is not a method of privacy protection. The DoH server that 
the client uses must be trusted. Additionally, DoH can not guaranty the security or dependability of the website being viewed.
Resource: RFC 8484, DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484

# Cybersecurity
In order to prevent a fake login page from stealing and using the login credentials, phishing-resistant MFA links login to the website. PKI-based smart cards, hardware
security keys, and FIDO2/WebAuthn passkeys comply with CISA regulations. These regulations do not apply to SMS codes, authenticator-app one-time passwords, or push 
approvals since they can be tricked into being disclosed. Phishing-resistant techniques must protect high-risk accounts for a login service.
Resource: CISA, Implementing Phishing-Resistant MFA - https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf

# Data
The Oman Personal Data Protection Law (Royal Decree 6/2022) mandates that data controllers obtain consent from data subjects, appoint a data protection officer, maintain 
a record of processing activities, and inform the Ministry within 72 hours of any significant data breach. To handle sensitive data, a permit from the Ministry is required,
and transferring data abroad necessitates a protection assessment. Stateadministrative bodies are excluded from the Oman Personal Data Protection Law. A separate Personal 
Data Protection Policy (Circular 6/2024) applies to these entities.
Resource: MTCIT, Personal Data Protection - https://mtcit.gov.om/sectors/governance/personal

# Misconception in My Track
It's a widespread misperception that authenticator-app OTPs and SMS codes are MFA techniques. These techniques are actually susceptible to phishing since attackers can 
fool users into divulging their authentication details. By binding authentication to the website, phishing-resistant MFA stops credentials from being stolen and used on 
phony login pages. Phishing-resistant techniques include PKI-based cards, hardware security keys, and FIDO2/WebAuthn passkeys. Instead of depending on SMS codes or regular
push approvals, firms should utilize phishing-resistant MFA for high-risk accounts. This distinction is supported by the resource under the names "SMS or Voice" and "PKI-based authentication."

# Open Question
How can a national single sign-on service ensure that AI-based login detection remains accurate and fair while protecting users from cyberattacks?

# Overview
Because they only allow citizens to sign in to government services once, the six layers of a single sign-on service are interdependent. Software guidelines like OpenID Connect 
and OAuth 2.0 govern identity and access sharing. Since many residents use applications to sign in, permissions should be kept as minimal as possible. While network security 
uses methods like encrypted DNS to secure data while it's in transit, cybersecurity provides phishing-resistant authentication. Logins are detected by artificial intelligence,
however there are problems associated with it, such as prejudice and incorrect predictions. Laws pertaining to data protection establish guidelines for managing people' personal
information at all levels. Trust in the national single sign-on service might be damaged by a fault at any tier.This summary emphasizes how crucial multi-factor authentication
(MFA) is for defending high-risk accounts from phishing scams.




