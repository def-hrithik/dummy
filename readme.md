<p align="center">
  <img src="IMG-20260222-WA0080.jpg" width="100%" align="center" />
</p>

<div align="center">

# 🔗 CertChain - Decentralized Certificate Verification

### Powered by Google Developer Group MGMCET

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-363636?logo=solidity)](https://soliditylang.org/)

</div>

---

## 📖 Introduction

**CertChain** is a blockchain-based certificate verification system that leverages **Ethereum smart contracts** to create an **immutable registry** for academic and professional certificates. By moving away from centralized databases, CertChain ensures that once a certificate is issued, its authenticity can be verified by anyone, anywhere — without relying on a single point of failure or trust.

Our mission is to bring **transparency**, **security**, and **decentralization** to credential verification, making fraud a thing of the past.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🔐 **Immutable Record Storage** | Certificates are permanently stored on the Ethereum blockchain — tamper-proof and eternal |
| 👤 **Admin (Issuer) & Verifier Roles** | Clear separation of responsibilities with role-based access control |
| 📱 **Cryptographic QR Code Verification** | Generate and scan QR codes for instant certificate validation |
| 📦 **Bulk Certificate Processing** | Issue multiple certificates in a single batch operation for efficiency |

---

## 🛠 Tech Stack

| Layer | Technology | Details |
|-------|------------|---------|
| **Frontend** | React.js | Modern, component-based UI framework |
| **Smart Contracts** | Solidity | Ethereum-compatible smart contract language |
| **Blockchain Environment** | Hardhat / Truffle | Development, testing, and deployment framework |
| **Local Network** | Ganache | Network ID: `5777` · RPC: `http://127.0.0.1:7545` |
| **Wallet** | MetaMask | Browser extension for blockchain interaction |

---

## 🚀 Installation & Setup

### Prerequisites

Before you begin, ensure you have the following installed:

- ✅ **Node.js** v16 or higher — [Download](https://nodejs.org/)
- ✅ **Ganache** — Local blockchain for development — [Download](https://trufflesuite.com/ganache/)
- ✅ **MetaMask** — Browser wallet extension — [Install](https://metamask.io/)

### Step-by-Step Setup

#### 1️⃣ Clone the Repository

```bash
git clone https://github.com/gdg-mgmcet/certchain.git
cd certchain
```

#### 2️⃣ Install Dependencies

```bash
npm install
```

#### 3️⃣ Compile Smart Contracts

```bash
npx hardhat compile
```

#### 4️⃣ Start Ganache

Open Ganache and create a new workspace with:
- **Port:** 7545
- **Network ID:** 5777

#### 5️⃣ Deploy Contracts to Local Network

```bash
npx hardhat run scripts/deploy.js --network ganache
```

#### 6️⃣ Configure MetaMask

1. Import a Ganache account using its private key
2. Add a custom network with RPC URL: `http://127.0.0.1:7545`

#### 7️⃣ Start the Frontend

```bash
npm start
```

> 🌐 Open [http://localhost:3000](http://localhost:3000) in your browser

---

> ⚠️ **SECURITY WARNING**
>
> **NEVER commit `.env` files or private keys to version control!**
>
> Add `.env` to your `.gitignore` file and use environment variables for sensitive data.

---

## 📋 Contribution Guidelines

<div align="center">

### ⚠️ STRICT GOVERNANCE RULES ⚠️

*Please read carefully before contributing*

</div>

We welcome contributions from the community! However, to maintain code quality, security, and backward compatibility, all contributors **MUST** adhere to the following rules:

---

### 📌 Rule 1: Branch Strategy

> **Create a new branch for EVERY feature or bug fix.**

```bash
git checkout -b feature/your-feature-name
```

Never commit directly to `main` or `develop` branches.

---

### 📌 Rule 2: Smart Contract Integrity (⚡ MOST IMPORTANT)

> **DO NOT modify existing smart contracts.**

If you need to change business logic or add new functionality:

1. ✅ **CREATE a new contract file** (e.g., `CertificateV2.sol`)
2. ✅ Ensure backward compatibility with existing contracts
3. ❌ **NEVER** alter deployed contract logic
4. ❌ **NEVER** change function signatures in existing contracts

This rule ensures that previously issued certificates remain verifiable and that the integrity of the blockchain record is preserved.

---

### 📌 Rule 3: Demo Video Requirement

> **All Pull Requests MUST include a demo video.**

Your PR must contain a **public Google Drive link** to a video demonstrating:

- ✅ The feature in action
- ✅ Blockchain interaction (MetaMask transactions, contract calls)
- ✅ Before/after comparison (if applicable)

**Format:** `https://drive.google.com/file/d/YOUR_VIDEO_ID/view?usp=sharing`

PRs without demo videos will be **automatically rejected**.

---

## 🌟 Open Innovation Issues

The following issues are open for contribution. Choose one and build something impactful!

---

### 🔲 Issue 1: Cryptographic QR Code Verification

**Goal:** Bridge the gap between physical certificates and digital truth.

> Make verification as simple as taking a photo — ideal for HR managers and academic institutions.

#### Problem Statement

Currently, when an admin issues a certificate:

| Status | Feature |
|--------|---------|
| ✅ | Certificate ID is generated |
| ✅ | Blockchain hash is generated |
| ❌ | No QR code is generated |
| ❌ | No direct QR-based verification mechanism |

This limits ease of verification and prevents seamless mobile validation.

#### Proposed Enhancement

**During Certificate Issuance (Admin Side):**
- Generate a QR Code containing the certificate hash and ID
- Embed the QR code in the digital certificate (PDF/image)
- Store QR reference in the database record

**During Verification (User Side):**
- User uploads or scans the QR code
- System decodes QR → extracts hash → queries blockchain
- Display result: ✅ Valid Certificate or ❌ Invalid Certificate

#### Acceptance Criteria

- [ ] QR code auto-generated on certificate issuance
- [ ] QR contains certificate hash or secure verification URL
- [ ] QR embedded in downloadable certificate
- [ ] Users can upload/scan QR to verify
- [ ] Clear verification result displayed

---

### 📦 Issue 2: Bulk Certificate Processing

**Goal:** Eliminate one-by-one certificate entry for institutions.

> Process entire graduating classes or workshop batches in a single operation.

#### Problem Statement

Current single-entry system creates:

- ⏱️ Time-consuming manual work
- ⚠️ Increased data entry errors
- 📉 Scalability limitations
- 🐢 Delays in blockchain issuance

For institutions handling hundreds of students, this is impractical.

#### Proposed Solution

Build a **Bulk Certificate Processing Module** that enables:

| Feature | Description |
|---------|-------------|
| 📄 File Upload | CSV / Excel / JSON format support |
| ✔️ Batch Validation | Validate all records before processing |
| 🔄 Auto Generation | Automated certificate creation |
| ⛓️ Bulk Hashing | Batch blockchain transactions |
| 📊 Status Tracking | Success / Failed / Pending per certificate |

#### Acceptance Criteria

- [ ] Upload file with multiple student records
- [ ] Bulk processing without manual entry
- [ ] Certificates correctly stored on blockchain
- [ ] Existing single-certificate flow remains unaffected

> ⚠️ **Important:** Create a NEW contract for this feature. Do NOT modify existing contracts.

---

### 🚀 Issue 3: Open Innovation

**Goal:** Contribute your own ideas to improve CertChain.

Have an idea that doesn't fit the above categories? We welcome innovative contributions in:

| Track | Examples |
|-------|----------|
| **UI/UX** | Dark mode, accessibility, mobile-first design |
| **Security** | Audit reports, penetration testing, vulnerability fixes |
| **Infrastructure** | CI/CD pipelines, Docker setup, testing frameworks |
| **Scalability** | Gas optimization, Layer 2 research, IPFS integration |

Open an issue to discuss your proposal before starting development.

---

## 🔒 Security Standards

All smart contract contributions **MUST** pass security verification before submission.

### Mandatory Security Checks

Run at least one of the following tools on your contracts:

| Tool | Purpose | Command |
|------|---------|---------|
| **Slither** | Static analysis for vulnerabilities | `slither .` |
| **Mythril** | Security analysis and bug detection | `myth analyze contracts/YourContract.sol` |

### Security Checklist

Before submitting your PR, ensure:

- [ ] No reentrancy vulnerabilities
- [ ] Proper access control implemented
- [ ] Integer overflow/underflow protected (Solidity ^0.8.0+)
- [ ] No hardcoded sensitive values
- [ ] Gas optimization reviewed
- [ ] All tests passing

---

## 🤝 Community & Support

<div align="center">

**CertChain** is a learning platform managed by **Google Developer Group MGMCET**.

Whether you're a blockchain beginner or an experienced developer, this project offers opportunities to learn, contribute, and grow with a supportive community.

---

### 💬 Our Motto

> *"Code responsibly. Build securely. Contribute confidently."*

---

### Get Involved

- 🐛 **Found a bug?** Open an issue
- 💡 **Have an idea?** Start a discussion
- 🤝 **Want to contribute?** Read our [CONTRIBUTING.md](CONTRIBUTING.md)
- ❓ **Need help?** Reach out to the GDG MGMCET team

</div>

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Built with ❤️ by Google Developer Group MGMCET**

*Empowering developers. Securing credentials. Building the future.*

</div>
