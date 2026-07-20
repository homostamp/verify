# 🛡️ HomoStamp Independent Blockchain Validator

A fully decentralized, client-side verification tool for **HomoStamp** certificates and digital proofs. This tool allows anyone to independently verify the authenticity of timestamped files directly against the **Polygon Blockchain** and the **Time Stamping Authority (TSA)** without relying on our central servers.

---

## 🚀 Key Features

*   **100% Serverless & Domain-Independent:** Runs entirely in your web browser. No databases, no tracking, and no proprietary backend dependencies.
*   **Direct Blockchain Queries:** Connects straight to the Polygon RPC network using standard Web3 libraries (`ethers.js`).
*   **Local Cryptographic Hashing:** Your source files never leave your computer. Hashing is performed locally in your browser using `crypto-js`.
*   **TSA Validation Ready:** Designed to work alongside industry-standard Time Stamping Authority responses.

---

## 🔍 Verification Formula & Logic

To guarantee that a document hasn't been tampered with and was anchored at a specific point in time, the validator implements a rigid cryptographic binding formula:

`$$finalHash = \text{SHA-256}(\text{verification\_code} + \text{tsa\_serial} + \text{sha256\_hash})$$`

1.  **Verification Code:** The unique system prefix (e.g., `HS-XXXXXXXXXXXX`).
2.  **TSA Serial:** The official serial number issued by the Time Stamping Authority.
3.  **SHA-256 Hash:** The lowercase cryptographic digest of the original file.

These components are concatenated in exact sequential order and passed through a final SHA-256 round. The resulting `finalHash` must match the transaction data immutable stored on the Polygon smart contract.

---

## 🛠️ How to Run Locally

Since this utility is completely autonomous, you can host it anywhere or even run it offline:

1.  **Clone or Download** this repository.
2.  Open the `index.html` file by double-clicking it to launch it directly in any modern browser (`file:///` protocol supported).
3.  Drop your file, paste the certificate parameters, and query the ledger directly.

---

## 🌐 Deployment

This repository is configured to deploy automatically via **GitHub Pages**. 
You can view the live, production-ready version of this validator anytime at:
`https://homostamp.github.io/verify/`

---

*Securing digital trust, independently.*
