# 🔒 LB1004 - Secure CI/CD Pipeline Transformation  
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

## 🏆 Outcome
- Established a **Trusted Software Supply Chain** aligned with **SLSA Level 3** standards.  
- Shifted security **left in the SDLC** without impacting developer productivity.  
- Enabled a pipeline that **detects, blocks, and remediates vulnerabilities automatically**.  

---

## 📖 Bonus Lab
👉 *Building a Trusted Pipeline with OpenShift Pipelines and Tekton* (alternative to Jenkins).  

---

## 👨‍💻 Authors
- Red Hat Workshop Team  
- Contributions & hands-on implementation by **[Your Name]**

---

## 🔗 References
- [Red Hat OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift)
- [Sigstore & Cosign](https://sigstore.dev)
- [SonarQube](https://www.sonarqube.org)
- [SLSA Framework](https://slsa.dev)

