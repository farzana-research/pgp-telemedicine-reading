# Notes on "PGP: Pretty Good Privacy" – Intro Chapter

## 1. What is PGP?

PGP is a program for protecting **email and files** using cryptography. It provides:

- **Encryption** for files and email (historically using IDEA as the symmetric cipher).
- **Digital signatures** to prove that messages/files come from the claimed sender and have not been modified.
- **Key management**: creation and storage of public/secret keys and a public-key "address book" (keyring).
- **Key certification**: signing other people’s public keys (basis of the Web of Trust).
- **Revocation and escrow**: revoking, disabling, or safely storing keys if they are compromised.
- **Configuration and key servers**: customizable settings and interaction with Internet key servers.

In short, PGP is a **toolbox for confidentiality, integrity, and authentication** of data.

## 2. What security goals does it address?

The book frames PGP within classic computer-security goals:

- **Privacy (confidentiality)** – keeping private data from unauthorized readers.
- **Integrity** – ensuring that data is not changed without detection.
- **Authentication** – ensuring that users and systems are who they claim to be.
- **Availability** – making sure systems and data are accessible when needed (PGP contributes indirectly).

PGP mainly focuses on **privacy, integrity, and authentication** for email and files. Other aspects (physical security, access control, management policies) must complement it.

## 3. Why do we need PGP? (Why email is vulnerable)

The intro explains that email behaves more like an **electronic postcard** than a sealed envelope:

- Messages pass through multiple intermediate machines on the network; each can copy or read the message.
- Messages often sit on servers before being read, where administrators or attackers could access them.
- Network links and local networks can be tapped; screen/display paths can also be intercepted.
- Misdelivery is common: messages sometimes go to the wrong recipient, which can leak sensitive content.

Because of this, **unencrypted email is not private**. PGP is presented as the “envelope + seal + signature” layer that email never had by default.

## 4. Using encryption well (and the danger of using it badly)

The book emphasizes:

> Using encryption badly is worse than not using it at all.

If users **believe** their encryption is secure but it is weak or misused, they may share highly sensitive information without appropriate caution. Good encryption must be:

- Cryptographically sound,
- Configured correctly,
- Embedded in a broader **security strategy** (passwords, policies, physical security, etc.).

## 5. Historical context: Where did PGP come from?

Key points:

- Phil Zimmermann began writing PGP in the mid-1980s and released version 1.0 in 1991 as **free software**.
- Early PGP used patented public-key algorithms (e.g., RSA) without a license, making it legally problematic in the US.
- PGP spread rapidly, especially outside the US, despite export-control restrictions on cryptographic software.
- Zimmermann and PGP faced legal and political pressure (crypto seen as "munitions"), but PGP still became a de facto standard for email encryption and signatures.

This background explains why PGP has both a **strong privacy reputation** and a **complicated legal and standardization history**.

## 6. My takeaways (for telemedicine context)

- PGP gives **practical tools** (file/email encryption, signatures, key management) that can be applied to **medical documents** (e.g., reports, lab results).
- The emphasis on **using encryption correctly** is crucial in telemedicine, where misuse could expose sensitive patient data.
- The "postcard vs envelope" analogy for email motivates using PGP on top of TLS to protect data not only in transit but also at rest and across multiple systems.
