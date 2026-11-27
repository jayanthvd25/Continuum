Project Polaris – Section 1: Key Findings

1. Core Concepts

* Offline Payment: Transfer of digital value between devices without requiring a connection to a central ledger.
* Double-Spending: Spending the same digital value more than once.
* Operational Modes: Fully offline, intermittently offline and staged offline.
* Trust Anchors: Hardware-based, software-based or hybrid mechanisms that establish security.
* Central Ledger: The authoritative system that maintains transaction and balance records.

2. Important Technical Insights

* Offline transactions cannot always rely on real-time central verification.
* Different environments require different offline payment architectures.
* Secure Elements (SE) and Trusted Execution Environments (TEE) can protect sensitive operations.
* Cryptographic mechanisms help authenticate transactions and protect digital value.
* Offline systems must handle synchronization, device failure, fraud and double-spending.
* Privacy must be balanced with regulatory requirements such as AML and CFT.

3. Relevance to Continuum

1. Investigate device-to-device communication for offline transactions.
2. Design an offline transaction validation mechanism.
3. Research double-spending prevention techniques.
4. Explore hardware-backed cryptographic key storage.
5. Design local transaction storage and synchronization.
6. Investigate secure recovery mechanisms for lost or damaged devices.

4. Open Research Questions

* How can two devices authenticate an offline transaction?
* How can we prevent double-spending without real-time central verification?
* How should offline transactions synchronize after reconnection?
* How can digital value be securely stored on a device?
* What happens if a device containing offline funds is destroyed?

Key Takeaway: Continuum must be designed around secure offline transaction validation, double-spending prevention, device security and reliable synchronization.


Section 2: Key Technical Concepts

1. Offline Value Transfer

* Digital value is transferred directly between devices without contacting a central ledger.
* Uses local communication technologies such as NFC.
* Enables payments during internet outages.
* Requires local transaction validation and double-spending prevention.

2. Three Modes of Offline Operation

Mode	Description
Fully Offline	Transactions happen without requiring central synchronization.
Intermittently Offline	Devices transact offline and periodically synchronize with the central system.
Staged Offline	Payment instructions are exchanged offline, but funds become settled after online verification.

Continuum Decision: Intermittently Offline.

3. Security Architectures

* Hardware-based: Uses Secure Elements (SE) to protect cryptographic keys and sensitive operations.
* Software-based: Uses cryptography, authentication and software security mechanisms.
* Hybrid: Combines hardware protection with software controls.

Continuum Decision: Initially explore software-based security, with future investigation of hardware-backed key storage.

4. Risk-Based Design

Security controls must be incorporated during initial architecture design.

Important mechanisms:

* Maximum offline transaction limits.
* Maximum offline wallet balance.
* Transaction frequency limits.
* Offline validity periods.
* Device revocation.
* Lost-device recovery.

5. Important Security Concepts

* Authentication: Verifies whether a transaction is authorised.
* Integrity: Ensures transaction information has not been modified.
* Double-Spending: Prevents the same digital value from being spent multiple times.
* Synchronization: Transfers locally stored transaction records to the central system after reconnection.

Relevance to Continuum

1. Smartphone-to-payment-terminal communication using NFC.
2. Offline transaction validation.
3. Public-key cryptography and digital signatures.
4. Secure local transaction storage.
5. Double-spending prevention.
6. Periodic synchronization and reconciliation.
7. Offline transaction limits.

Key Takeaway: Continuum needs a secure local transaction protocol that supports payments without internet connectivity while controlling double-spending risks and enabling synchronization after reconnection.