# 🚀 Secure Azure Application Deployment (ACI + Private SQL + App Gateway + VPN)

![Azure](https://img.shields.io/badge/Azure-Cloud-blue?logo=microsoftazure)
![Terraform](https://img.shields.io/badge/IaC-Terraform-purple?logo=terraform)
![DevOps](https://img.shields.io/badge/DevOps-CI%2FCD-green?logo=azuredevops)
![SQL](https://img.shields.io/badge/Database-Azure%20SQL-orange?logo=databricks)
![Networking](https://img.shields.io/badge/Networking-VNet%20%7C%20VPN-red?logo=cloudflare)
![Security](https://img.shields.io/badge/Security-WAF%20%7C%20PrivateLink-yellow?logo=security)

> 🌟 **End-to-End Secure Deployment of a Containerized Application on Azure — leveraging ACI, Private SQL, Application Gateway (HTTPS/WAF), and VPN connectivity.**

---

## 📌 Project Overview  

This project demonstrates how to **deploy a secure cloud-native application** using:  

- **Azure Container Instances (ACI)** for containerized workloads  
- **Azure SQL Database (Private Endpoint)** for secure DB connectivity  
- **Application Gateway (WAF v2)** to expose the app securely over HTTPS  
- **VPN Gateway (Point-to-Site)** for developer/private access  
- **Terraform + Azure DevOps Pipelines** for full automation  

✅ **Goal:** Deliver production-ready infrastructure with **private network isolation**, **secure HTTPS exposure**, and **end-to-end CI/CD automation**.  


---
## 📌 Tech Stack  

| Category              | Tools & Services |
|------------------------|-----------------|
| **Cloud**             | Azure (ACI, SQL, App Gateway, Key Vault, VPN, Private DNS, Log Analytics) |
| **IaC**               | Terraform (modular structure) |
| **CI/CD**             | Azure DevOps Pipelines |
| **Containerization**  | Docker + ACR |
| **Security**          | NSG, RBAC, Managed Identity, WAF v2 |
| **Monitoring**        | Log Analytics, Flow Logs, AppGW Insights |
---

## 🏗️ Architecture  

```mermaid
graph TD
    Dev[👨‍💻 Developer] -->|VPN P2S| VPNGW[🔒 VPN Gateway]
    VPNGW --> VNet[VNet - Private Subnet]
    VNet --> ACI[📦 Azure Container Instance]
    VNet --> SQL[(💾 Azure SQL Private Endpoint)]
    ACI -->|HTTP:8080| AppGW[🌐 Application Gateway]
    Client[🌍 User] -->|HTTPS:443| AppGW
    AppGW --> ACI


