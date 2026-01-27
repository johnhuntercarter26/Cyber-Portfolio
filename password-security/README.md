# Password Security & Cracking Analysis

## Abstract
Abstract
In an era where digital security becomes a larger priority every day, weak passwords remain as one of the largest vulnerabilities in cybersecurity. Despite advancements in authentication methods, users continue to rely on incredibly simple passwords, making them susceptible to attacks. While extensive research exists on password security, there is a gap in practical analysis comparing different password-cracking methods and their effectiveness against varying levels of password complexity.

Passwords are not stored in plaintext; instead, they are saved in a hashed format using cryptographic algorithms such as MD5, SHA-256, and bcrypt. Since hashing is an irreversible process, attackers cannot directly retrieve the original password from the hash and rely on password-cracking tools that attempt to determine the corresponding plaintext password for a given hash. This research evaluates the efficiency of several different methods of password attack, such as dictionary, hybrid, rainbow table, brute force, and credential stuffing. The experiment will take place in a controlled testing environment, where password hashes will be generated and analyzed for their susceptibility to various attack techniques.

Analyzing how quickly each tool can crack passwords of varying complexity will demonstrate the real-world risks of using weak passwords and return results of which hashing methods are the most secure. Additionally, this research will explore modern best practices, including the use of MFA, password managers, passphrases, etc. The argument to be made is that current password policies often fail to protect users from consistently changing threats. Providing real evidence on password vulnerabilities means that this study can offer actionable recommendations for improving password security, strengthening cybersecurity defenses against unauthorized access for everyday people

## Context
This project was originally completed as an academic poster. The original poster is unavailable, but the abstract reflects the scope and findings.

## Tools Used
- Hashing Algorithms (MD5, SHA, Bcrypt)
- Password Cracking tools (Hashcat, John the Ripper)

## Key Takeaway
- Password length and randomness matter more than complexity rules alone
- Weak or reused passwords are quickly cracked using common wordlists
- Hashing significantly increases resistance to password cracking compared to plaintext storage
- Salting hashes reduces the effectiveness of precomputed attacks
- User education and strong password policies are critical for real-world security

## Presented at the University of North Georgia Annual Research Conferenece
## https://arc.ungjournals.org/articles/157
