🌐 AWS 3-Tier Web Application Architecture with Disaster Recovery

This project demonstrates a production-grade 3-Tier Web Application setup on AWS, complete with a Disaster Recovery (DR) environment using cross-region infrastructure.

It’s designed for high availability, fault tolerance, and data resiliency — ideal for hosting modern web applications in a secure and scalable manner.

🏗️ Architecture Overview

The setup is divided into two main regions:

- Primary Region (`ap-south-1`)
- Disaster Recovery Region (`ap-south-2`)

Each region contains a fully isolated 3-tier VPC structure:  
- 🔹 Frontend Tier (Web servers)
- 🔸 Application Tier(App servers)
- 🛢 Database Tier (RDS instances with replication)

![AWS 3-Tier DR Architecture](3-Tier-Arch.png)

🔐 Key Components

☁️ Primary Region (`ap-south-1`)
- VPC: `3-tier-prj-vpc`
- Web Servers: Auto Scaling Group (`web-server-ASG`)
- App Servers: Auto Scaling Group (`app-server-ASG`)
- Databases:
  - `PR-DB1`: Primary RDS instance
  - `PR-DB2`: Standby DB
- NAT Gateway for private subnet internet access
- Security Groups:
  - `frontend-sg`
  - `backend-sg`
 
🌩  Disaster Recovery Region (`ap-south-2`)
- VPC: `3-tier-prj-DR-vpc`
- Web & App Tiers: Standby Auto Scaling Groups
- RDS Read Replica: `DR-DB1` (cross-region replicated)
- Separate NAT Gateway & Security Groups

🔁 Cross-Region Replication

- Amazon RDS enables cross-region replication from the primary DB to the backup DB.
- Ensures data availability even if the primary region becomes unavailable.
- Route 53 handles failover DNS routing based on health checks.

🛠 Tools & Services Used

| Service       | Purpose                               |
|---------------|----------------------------------------|
| **EC2**       | Hosts web and app servers              |
| **RDS**       | Relational database with failover      |
| **Auto Scaling** | For app and web server scaling    |
| **NAT Gateway** | Internet access for private instances|
| **Route 53**  | DNS management and failover routing    |
| **VPC/Subnets** | Full network segmentation            |
| **Security Groups** | Layered access control          |


📄 Files in this Repository

| File Name              | Description                        |
|------------------------|------------------------------------|
| `3-Tier-Arch.drawio`   | Editable architecture diagram       |
| `3-Tier-Arch.png`      | Rendered architecture image         |
| `3-Tier-Arch.pdf`      | Printable architecture document     |
| `3-Tier-Arch.html`     | Web export from Draw.io             |
| `README.md`            | This project documentation          |


✍️ Author

Dinesh Kumar D
📧 dineshkumar.d232005@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/dineshkumar-d-b54a21325/)

💡 Want to Contribute?

Feel free to fork this repository or open an issue if you'd like to expand the design, deploy it with Terraform, or add monitoring tools.
