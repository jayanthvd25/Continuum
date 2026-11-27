Continuum – Initial Design Decisions

Category	Selected Approach
Target Environment	Urban environments (metro stations, public transport, retail)
Operational Mode	Intermittently Offline
Security Approach	Hybrid security
Payment Architecture	Smartphone-to-Payment-Terminal
Communication Technology	NFC (Near Field Communication)
Transaction Storage	Local transaction database
Synchronization	Synchronization with central server when connectivity returns

Proposed Transaction Workflow

1. Passenger initiates a payment using the Continuum mobile wallet.
2. Passenger enters the payment amount.
3. Smartphone communicates with the payment terminal through NFC.
4. Devices authenticate and validate the transaction.
5. Transaction information is securely stored locally.
6. Both parties receive transaction confirmation.
7. When internet connectivity returns, pending transactions synchronize with the central server.
8. The central system reconciles the received transactions.

Core Technical Areas to Investigate

1. Offline transaction protocols.
2. Public-key cryptography and digital signatures.
3. Double-spending prevention.
4. NFC-based device communication.
5. Secure local transaction storage.
6. Transaction synchronization and reconciliation.
7. Fraud detection and replay attack prevention.

Initial Project Objective

To explore and develop an intermittently offline digital payment infrastructure that enables secure transactions between smartphones and payment terminals without requiring continuous internet connectivity.

Note: These are initial design choices. Their feasibility, security and limitations must be validated through further research and prototyping.


Section 2 – Important Design Considerations

1. Operational Mode

* Continuum will initially explore an Intermittently Offline architecture.
* Transactions can occur locally without continuous internet connectivity.
* Devices synchronize transaction records with the central server when connectivity returns.
* Offline spending limits may help reduce double-spending risks.

2. Hybrid Security Model

* Combine software-based transaction validation with hardware-backed key protection.
* Investigate Android Keystore/StrongBox and Apple’s Secure Enclave.
* Use cryptographic signatures to verify transaction authenticity and integrity.
* Protect local transaction state against manipulation.
* Hardware-backed key storage alone does not prevent double spending.

3. Existing Device Infrastructure

* Prefer existing consumer smartphones and compatible payment terminals.
* Avoid developing custom hardware initially.
* Investigate NFC as the primary communication technology for the metro use case.
* Terminal compatibility must be validated; ordinary bank POS terminals may not support custom offline payment protocols.

4. Online–Offline Transition

* Detect internet connectivity automatically.
* Switch to the supported offline transaction workflow when connectivity is unavailable.
* Store transaction records locally.
* Synchronize pending transactions when connectivity is restored.
* Handle failed synchronization and conflicting transaction records.

5. Lost-Value Recovery

* Consider scenarios where a phone is lost, damaged, or destroyed before synchronization.
* Define how offline funds and pending transactions can be recovered.
* Prevent duplicate recovery claims and double spending.
* Treat this as an important production-level requirement.

6. Privacy and Regulatory Compliance

* Minimize unnecessary personal and transaction metadata.
* Balance user privacy with fraud detection and regulatory requirements.
* Consider AML (Anti-Money Laundering) and CFT (Combating the Financing of Terrorism) requirements.
* Design appropriate auditing and monitoring mechanisms during synchronization.

Initial Design Direction for Continuum

Component	Initial Direction
Target Environment	Urban public transport / Metro stations
Operational Mode	Intermittently Offline
Payment Architecture	Smartphone-to-Payment-Terminal
Communication	NFC
Security	Hybrid
Device Infrastructure	Existing smartphones and compatible terminals
Transaction Storage	Local database
Connectivity Handling	Automatic online/offline transition
Synchronization	Periodic synchronization with central server
Lost-Value Recovery	Production-level requirement
Privacy	Privacy-conscious transaction design

Key Takeaway

Continuum should prioritize secure offline transactions, reliable synchronization, double-spending prevention, and compatibility with existing devices.

Note: These are initial design directions, not finalized implementation decisions. They must be validated through protocol design, threat modelling, and hardware compatibility testing.

