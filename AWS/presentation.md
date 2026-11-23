# Introduction to AWS Cloud
## Hosting a web application in the cloud

Marwan Bouhamid · SOLICODE Tanger
M4: Déployer une solution logicielle

---

## 1. What is Cloud Computing?

- Renting IT resources (servers, storage, databases) over the internet
- No need to buy and maintain your own physical servers
- Pay-as-you-go: you pay for what you use
- Resources can be increased or reduced when needed

---

## 2. What is AWS?

- Amazon Web Services: a cloud platform offering 200+ services
- Infrastructure is organized in Regions (geographic areas)
- Each Region contains several Availability Zones (separate data centers)
- Used by startups, companies and public institutions worldwide

---

## 3. Core Services for a Web Developer

| Service | Role |
|---|---|
| **EC2** | Virtual servers to run your app |
| **S3** | Storage for files and images |
| **RDS** | Managed databases (MySQL, PostgreSQL...) |
| **IAM** | Users, roles and permissions |
| **Route 53** | Domain names (DNS) |
| **CloudFront** | Content delivery (CDN), faster loading |

---

## 4. Example: a Laravel App on AWS

User (browser / phone)  →  EC2 (Laravel + PHP)  →  RDS (MySQL database)
                                                 →  S3 (uploaded files)

The user sends a request, EC2 runs the app, RDS stores data, S3 stores files.

---

## 5. Benefits and Points of Attention

- **Benefits:** scalability, global reach, many managed services
- **Cost:** unused or forgotten resources can create unexpected bills
- **Security:** AWS secures the cloud; you secure your configuration (shared responsibility)
- **Good habits:** use IAM users with limited permissions, set billing alerts

---

## 6. Conclusion

- AWS lets developers deploy and scale applications without owning servers
- EC2, RDS and S3 cover the basic needs of a web project
- Start small, watch costs, and secure access from day one
- Thank you! Questions?