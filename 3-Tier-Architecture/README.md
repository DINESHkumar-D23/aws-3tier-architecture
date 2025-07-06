# AWS 3-Tier Architecture with Disaster Recovery





\# AWS 3-Tier Architecture with Disaster Recovery



This project demonstrates a production-grade 3-tier architecture in AWS, with a Disaster Recovery (DR) setup across regions.



\## 🏗️ Architecture Overview



\- \*\*Web Layer\*\*: Deployed in a public subnet behind a load balancer.

\- \*\*App Layer\*\*: Private subnet with NAT Gateway access.

\- \*\*Database Layer\*\*: RDS hosted in a private subnet with cross-region replication.

\- \*\*NAT Gateway\*\*: Enables outbound traffic for private subnets.

\- \*\*Internet Gateway\*\*: Handles public traffic for web tier.

\- \*\*Security Groups\*\*: Isolated rules between layers.



\## 📁 Files Included



| File Name            | Description                        |

|----------------------|------------------------------------|

| `3-Tier-Arch.drawio` | Editable Draw.io architecture file |

| `3-Tier-Arch.png`    | Architecture image                 |

| `3-Tier-Arch.pdf`    | Printable PDF version              |

| `3-Tier-Arch.html`   | Web-exported Draw.io version       |

| `README.md`          | Project overview                   |



\## ✍️ Author



\*\*Dinesh Kumar D\*\*  

📧 dineshkumar.d232005@gmail.com  

🔗 \[LinkedIn](https://www.linkedin.com/in/dineshkumar-d-b54a21325/)



