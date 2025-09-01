# 🚀 Project 3 — CI/CD Pipeline to S3 Website  

## 📌 Goal  
Automate deployments from **GitHub → AWS CodePipeline → CodeBuild → S3 (static website)** with **SNS notifications**.  
This project demonstrates automation, IaC basics, and DevOps fundamentals for the resume.  

---

## 🏗️ Architecture (High-Level Flow)  

1. **GitHub Repo** (source code: `index.html`, `buildspec.yml`)  
2. **CodePipeline** (orchestrates the workflow)  
   - **Source Stage**: connects to GitHub branch  
   - **Build Stage**: CodeBuild runs sanity checks & deploy script  
   - **Deploy Stage**: artifacts uploaded to S3 website bucket  
3. **S3 Buckets**  
   - **Artifact bucket** → stores pipeline packages  
   - **Website bucket** → hosts static website  
4. **SNS Topic** → email notifications for success/failure  
5. **IAM Roles** → least-privilege for CodePipeline + CodeBuild  



## 📂 Repo Layout  

```bash
/project-3-cicd-s3
  ├── app/
  │   └── index.html          # Simple static site showing deployment info: + version string
  ├── buildspec.yml           # CodeBuild instructions
  ├── arch/
  │   └── diagram.png         # architecture diagram
  ├── README.md               # project documentation
  
      └── budget-alarms.md    # simple budget + alarm notes
