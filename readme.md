<p align="center">
  <img src="IMG-20260222-WA0080.jpg" width="150" alt="CertChain Logo" />
</p>

<div align="center">

# CertChain - Decentralized Certificate Verification

### Powered by Google Developer Group MGMCET

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-363636?logo=solidity)](https://soliditylang.org/)

</div>

---

## Introduction

**CertChain** is a blockchain-based certificate verification system that leverages **Ethereum smart contracts** to create an **immutable registry** for academic and professional certificates. By moving away from centralized databases, CertChain ensures that once a certificate is issued, its authenticity can be verified by anyone, anywhere — without relying on a single point of failure or trust.

The project aims to bring **transparency**, **security**, and **decentralization** to credential verification.

---

## Development Standards

To maintain code quality, security, and backward compatibility, all contributors must adhere to the following governance standards.

| Standard | Requirement | Consequence |
|----------|-------------|-------------|
| **Branching** | Create a new branch for every feature or bug fix | Direct commits to `main` or `develop` are prohibited |
| **Contract Integrity** | Do not modify existing smart contracts | Create new contract files for new functionality |
| **Demo Video** | All PRs must include a Google Drive video link | PRs without demos will be rejected |

---

### Branching Strategy

```bash
git checkout -b feature/your-feature-name
```

---

### Smart Contract Integrity

If business logic changes or new functionality is required:

| Action | Status |
|--------|--------|
| Create a new contract file (e.g., `CertificateV2.sol`) | Required |
| Ensure backward compatibility with existing contracts | Required |
| Alter deployed contract logic | Prohibited |
| Change function signatures in existing contracts | Prohibited |

This standard ensures that previously issued certificates remain verifiable and that the integrity of the blockchain record is preserved.

---

### Demonstration Requirement

The Pull Request must contain a public Google Drive link to a video demonstrating:

| Requirement | Description |
|-------------|-------------|
| Feature Demo | The feature in action |
| Blockchain Interaction | MetaMask transactions, contract calls |
| Comparison | Before/after comparison (if applicable) |

**Format:** `https://drive.google.com/file/d/YOUR_VIDEO_ID/view?usp=sharing`

---

## Open Innovation Tracks

| Track | Goal | Contract Rule |
|-------|------|---------------|
| QR Code Verification | Bridge physical certificates and digital verification | Use existing contract |
| Bulk Certificate Processing | Eliminate manual entry for institutions | Create NEW contract |
| General Improvements | UI/UX, Security, Infrastructure, Scalability | Depends on scope |

---

### 1. Feature Request: Cryptographic QR Code Verification

**Goal:** Bridge the gap between physical certificates and digital verification.

#### Problem Statement

| Current State | Status |
|---------------|--------|
| Certificate ID generated | Yes |
| Blockchain hash generated | Yes |
| QR code generated | No |
| QR-based verification mechanism | No |

This limits ease of verification and prevents seamless mobile validation.

#### Proposed Enhancement

| Phase | Action |
|-------|--------|
| **Issuance (Admin)** | Generate QR Code containing certificate hash and ID |
| | Embed QR code in digital certificate (PDF/image) |
| | Store QR reference in database record |
| **Verification (User)** | Upload or scan QR code |
| | System decodes QR, extracts hash, queries blockchain |
| | Display result: Valid or Invalid Certificate |

#### Acceptance Criteria

| Criteria | Status |
|----------|--------|
| QR code auto-generated on certificate issuance | [ ] |
| QR contains certificate hash or secure verification URL | [ ] |
| QR embedded in downloadable certificate | [ ] |
| Users can upload/scan QR to verify | [ ] |
| Clear verification result displayed | [ ] |

---

### 2. Feature Request: Bulk Certificate Processing

**Goal:** Eliminate manual certificate entry for institutions.

#### Problem Statement

| Issue | Impact |
|-------|--------|
| Single-entry system | Time-consuming manual work |
| Manual data entry | Increased error rate |
| No batch processing | Scalability limitations |
| Sequential blockchain calls | Delays in certificate issuance |

#### Proposed Solution

Build a **Bulk Certificate Processing Module**:

| Feature | Description |
|---------|-------------|
| File Upload | CSV / Excel / JSON format support |
| Batch Validation | Validate all records before processing |
| Auto Generation | Automated certificate creation |
| Bulk Hashing | Batch blockchain transactions |
| Status Tracking | Success / Failed / Pending per certificate |

#### Acceptance Criteria

| Criteria | Status |
|----------|--------|
| Upload file with multiple student records | [ ] |
| Bulk processing without manual entry | [ ] |
| Certificates correctly stored on blockchain | [ ] |
| Existing single-certificate flow remains unaffected | [ ] |

**Note:** Create a NEW contract for this feature. Do not modify existing contracts.

---

### 3. General Improvements

**Goal:** Contribute ideas to improve CertChain.

| Track | Examples |
|-------|----------|
| UI/UX | Dark mode, accessibility, mobile-first design |
| Security | Audit reports, penetration testing, vulnerability fixes |
| Infrastructure | CI/CD pipelines, Docker setup, testing frameworks |
| Scalability | Gas optimization, Layer 2 research, IPFS integration |

Open an issue to discuss proposals before starting development.

---

## Security Standards

All smart contract contributions must pass security verification before submission.

### Mandatory Security Checks

| Tool | Command | Purpose |
|------|---------|---------|
| Slither | `slither .` | Static analysis for vulnerabilities |
| Mythril | `myth analyze contracts/YourContract.sol` | Security analysis and bug detection |

### Security Checklist

| Requirement | Status |
|-------------|--------|
| No reentrancy vulnerabilities | [ ] |
| Proper access control implemented | [ ] |
| Integer overflow/underflow protected (Solidity ^0.8.0+) | [ ] |
| No hardcoded sensitive values | [ ] |
| Gas optimization reviewed | [ ] |
| All tests passing | [ ] |

---

## Community

CertChain is a learning platform managed by **Google Developer Group MGMCET**.

### Motto

> "Code responsibly. Build securely. Contribute confidently."

### Get Involved

| Action | How |
|--------|-----|
| Found a bug? | Open an issue |
| Have an idea? | Start a discussion |
| Want to contribute? | Read [CONTRIBUTING.md](CONTRIBUTING.md) |
| Need help? | Reach out to GDG MGMCET team |

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Maintained by Google Developer Group MGMCET**

</div>

