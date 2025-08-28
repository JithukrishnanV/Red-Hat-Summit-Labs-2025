# 🔒Secure CI/CD Pipeline Transformation  

![RedHatSummit2](https://github.com/user-attachments/assets/b70cafa5-1bda-4ac1-b883-8e12430afc69)

**From Development to Deployment: Securing the Software Supply Chain with Jenkins & Red Hat Advanced Developer Suite (RHADS)**

## 📌 Overview
This project demonstrates how to transform a **non-secure CI/CD pipeline** into a **Trusted Software Supply Chain** using:  
- **Red Hat OpenShift**
- **Red Hat Developer Hub (RHDH)**
- **Red Hat Advanced Developer Suite (RHADS)**
- **Security Tools**: Sigstore/Cosign, TUF, SonarQube, Red Hat Advanced Cluster Security (ACS), and Trusted Profile Analyzer (TPA).

The workshop follows a narrative journey, showcasing roles of **developers, QA engineers, and security engineers**, highlighting challenges of insecure practices and how RHADS addresses them with guardrails and automation.

---

## 🚀 Key Features Implemented
### 1. **Signed Commits**
- Enforced cryptographically signed Git commits using **Gitsign**.  
- Prevents unverified/unauthorized changes from entering the pipeline.

### 2. **Signed Container Images**
- Generated **Cosign key pairs** and integrated signing into the build process.  
- Configured a **TUF mirror registry** for trusted signing metadata.  

### 3. **Software Bill of Materials (SBOM)**
- Automatically generated SBOMs during builds.  
- Uploaded SBOMs to **CycloneDX repository** and **TPA** for vulnerability analysis and compliance tracking.

### 4. **Vulnerability Scanning & Policy Enforcement**
- Integrated **SonarQube** for static code analysis.  
- Configured **Red Hat ACS** policies (e.g., Log4Shell detection, Trusted Signature Policy).  
- Enforced **0-Trusted Signature Policy** to block unsigned images.  

### 5. **Secure Build & Deploy Pipeline**
- Enhanced Jenkins pipeline with **7 new security tasks**:
  1. Verify Commit (Gitsign)
  2. Source Code Scan (SonarQube)
  3. Build & Sign Image (Cosign + SBOM)
  4. Upload SBOM to CycloneDX
  5. Upload SBOM to TPA
  6. ACS Image Check (Policy Enforcement)
  7. ACS Image Scan (CVE Detection)

- Validated deployments with **Enterprise Contract CLI (ec)** + Cosign.  
- Blocked insecure apps, allowed only signed + verified applications.

---

## 🛠️ Tech Stack
- **Platform**: Red Hat OpenShift  
- **CI/CD**: Jenkins, Tekton (Bonus Lab)  
- **Security**: Cosign, Sigstore, TUF, ACS, SonarQube, TPA  
- **Developer Tools**: RHDH, OpenShift Dev Spaces (VSCode)  

---

## 📸 Demo Highlights
- ✅ **Verified Commits** using Gitsign  
- ✅ **SBOM Generation & Upload** (CycloneDX + TPA)  
- ✅ **ACS Policies in Action** (Blocking insecure apps)  
- ✅ **Secure Deployments** with Cosign + Enterprise Contract CLI  
- ✅ **Transparent Guardrails** — Developers code as usual, security enforced automatically  

---

## 📚 Workshop Flow
1. **Chapter 1**: A Day in the Life of a New Developer  
   - Developer onboarding with **RHDH** and Internal Developer Portals.  

2. **Chapter 2**: Tightrope Walking without a Net  
   - QA discovers a compromised application → highlights lack of guardrails.  

3. **Chapter 3**: Red Hat Advanced Developer Suite to the Rescue  
   - Demonstration of **secure build and deploy pipeline** with RHADS.  

---
<img width="2491" height="1240" alt="image" src="https://github.com/user-attachments/assets/aaf6879a-aba4-4cd7-a7af-5f918652d6f3" />
<img width="2233" height="1339" alt="image" src="https://github.com/user-attachments/assets/ecdd973f-ce68-42fe-a147-35e5814061cd" />

## 🏆 Outcome
- Established a **Trusted Software Supply Chain** aligned with **SLSA Level 3** standards.  
- Shifted security **left in the SDLC** without impacting developer productivity.  
- Enabled a pipeline that **detects, blocks, and remediates vulnerabilities automatically**.  

---
<img width="622" height="458" alt="image" src="https://github.com/user-attachments/assets/ec576211-af76-477e-ba7f-b5ac662df982" />

## 📖 Bonus Lab
👉 *Building a Trusted Pipeline with OpenShift Pipelines and Tekton* (alternative to Jenkins).  

---
<img width="2830" height="1714" alt="image" src="https://github.com/user-attachments/assets/50f73433-f293-4a4b-bdff-5d86a51709e8" />
<img width="2525" height="1348" alt="image" src="https://github.com/user-attachments/assets/d86641d7-c935-4248-b29f-ad579e21251a" />

## 👨‍💻 Authors
- Red Hat Workshop Team  
- Contributions & hands-on implementation by **[Your Name]**

---
<img width="2506" height="1240" alt="image" src="https://github.com/user-attachments/assets/eb9e4e2f-daae-4709-865d-78c8fdce47af" />

## 🔗 References
- [Red Hat OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift)
- [Sigstore & Cosign](https://sigstore.dev)
- [SonarQube](https://www.sonarqube.org)
- [SLSA Framework](https://slsa.dev)
