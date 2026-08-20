# Cloud Provider Comparison

This comparison examines how the three major public cloud providers offer similar infrastructure services. Although each provider uses different service names and features, their services generally address the same fundamental cloud computing requirements.

The information presented here is based on the official documentation of Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

---

## Infrastructure Service Comparison

| **Infrastructure Component** | **Amazon Web Services (AWS)** | **Microsoft Azure** | **Google Cloud Platform (GCP)** |
|---|---|---|---|
| **Compute** | Amazon EC2 | Azure Virtual Machines | Compute Engine |
| **Storage** | Amazon S3 | Azure Blob Storage | Cloud Storage |
| **Networking** | Amazon VPC | Azure Virtual Network | Virtual Private Cloud (VPC) |
| **Identity and Access Management (IAM)** | AWS IAM | Azure RBAC | Google Cloud IAM |

### Compute

Amazon EC2, Azure Virtual Machines, and Compute Engine provide virtual computing resources that can be used to run applications, services, and workloads in the cloud.

### Storage

Amazon S3, Azure Blob Storage, and Cloud Storage provide cloud-based storage for files, objects, and other types of data. These services allow organizations to store data without depending entirely on local physical storage.

### Networking

Amazon VPC, Azure Virtual Network, and Google Cloud VPC provide virtual networking environments for cloud resources. They allow resources to communicate while providing control over network configuration and access.

### Identity and Access Management

AWS IAM, Azure RBAC, and Google Cloud IAM provide mechanisms for controlling access to cloud resources. They allow administrators to determine who can access resources and what actions they are allowed to perform. AWS IAM uses policies to define permissions, while Azure RBAC uses roles and Google Cloud IAM uses roles and permissions. :contentReference[oaicite:0]{index=0}

---

## Guide Questions

### 1. Which cloud provider offers the broadest range of services?

AWS offers a very broad range of cloud services covering areas such as computing, storage, networking, databases, security, analytics, and other technologies. Its large service portfolio makes it suitable for organizations with different types of cloud requirements.

### 2. Which cloud platform would you recommend for an organization that primarily uses Microsoft products? Why?

I would recommend Microsoft Azure for an organization that primarily uses Microsoft products. Azure is closely connected with Microsoft's ecosystem, making it a practical choice for organizations already using Microsoft technologies and services.

### 3. Which platform is widely recognized for Artificial Intelligence (AI), Machine Learning (ML), and Kubernetes services?

Google Cloud is widely recognized for its capabilities in Artificial Intelligence, Machine Learning, and Kubernetes. Google Kubernetes Engine (GKE) provides managed Kubernetes infrastructure, while Google Cloud also provides infrastructure and services for AI and ML workloads. :contentReference[oaicite:1]{index=1}

### 4. What similarities did you observe among the three cloud providers?

All three providers offer services for the fundamental parts of cloud infrastructure, including compute, storage, networking, and identity and access management. Although their service names and specific features differ, the basic purpose of these services is similar across the three platforms.

---

## Official Resources

### Amazon Web Services (AWS)

- [Amazon EC2 — Compute](https://aws.amazon.com/ec2/)
- [Amazon S3 — Storage](https://aws.amazon.com/s3/)
- [Amazon VPC — Networking](https://aws.amazon.com/vpc/)
- [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/)

### Microsoft Azure

- [Azure Virtual Machines — Compute](https://learn.microsoft.com/en-us/azure/virtual-machines/)
- [Azure Blob Storage — Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/)
- [Azure Virtual Network — Networking](https://learn.microsoft.com/en-us/azure/virtual-network/)
- [Azure Role-Based Access Control (RBAC)](https://learn.microsoft.com/en-us/azure/role-based-access-control/)

### Google Cloud Platform (GCP)

- [Compute Engine — Compute](https://cloud.google.com/compute)
- [Cloud Storage — Storage](https://cloud.google.com/storage)
- [Virtual Private Cloud (VPC) — Networking](https://cloud.google.com/vpc)
- [Identity and Access Management (IAM)](https://cloud.google.com/iam)

---

## Tools and Assistance

- **GitHub** — repository hosting and version control
- **KillerCoda** — Cloud-based Linux environment
- **ChatGPT** — used for grammar checking, improving wording, organizing the documentation, and providing ideas.

---

## Conclusion

AWS, Microsoft Azure, and Google Cloud provide the fundamental infrastructure services needed to build and manage cloud-based systems. While the providers use different service names and implementations, the main concepts remain similar: compute resources run workloads, storage keeps data, networking connects resources, and identity and access management controls access to cloud resources.

Understanding these service equivalents is important for cloud engineers because the knowledge of one cloud platform can be applied when working with similar services on another platform.

