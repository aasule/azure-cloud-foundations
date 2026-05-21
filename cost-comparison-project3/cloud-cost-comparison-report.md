# Cloud Cost Comparison Report: AWS vs Azure for a Small Web Application

## Introduction

This project analyses the cost of hosting a small web application on both Amazon Web Services (AWS) and Microsoft Azure. The objective is to compare pricing models, infrastructure costs, networking charges, and discount mechanisms in order to determine the most cost-effective platform for a small business workload.

The comparison focuses on compute resources, storage, operating system licensing, and networking costs using the official pricing calculators from both cloud providers.

---

# 1. Application Requirements

## Application Description

The application used for this comparison is a small business web application that supports:

- User authentication and login
- Dashboard access
- File uploads
- Moderate monthly traffic

The application is assumed to run continuously throughout the month.

---

## Compute Requirements

| Component | Specification |
|---|---|
| Virtual Machine | 1 vCPU |
| Memory | 1 GB RAM |
| Operating System | Linux / Windows |
| Runtime | 730 Hours per Month |

---

## Storage Requirements

| Storage Type | Capacity |
|---|---|
| VM Disk Storage | 30 GB SSD |
| Object Storage | 50 GB |

---

## Equivalent Cloud Services

| AWS | Azure |
|---|---|
| EC2 t3.micro / t3.small | B1s / B1 Virtual Machine |
| S3 Storage | Azure Blob Storage |
| EBS Volume | Azure Managed Disk |

---

## Networking Assumptions

| Component | Estimate |
|---|---|
| Monthly Outbound Data Transfer | Moderate Traffic |
| Inter-Zone Data Transfer Test | Included for Comparison |

---

# 2. AWS Cost Estimation

The AWS pricing estimate was generated using Linux-based EC2 instances and S3 object storage.

## AWS Services Used

| Service | Purpose |
|---|---|
| EC2 | Virtual Machine Hosting |
| EBS | VM Disk Storage |
| S3 | Object Storage |
| Data Transfer | Networking/Egress |

---

## AWS Pricing Result

| Billing Period | Cost |
|---|---|
| Monthly Cost | $30.60 |
| Annual Cost | $367.20 |
| Upfront Cost | Included |

---

## AWS Pricing Analysis

The AWS estimate includes:

- Compute charges for EC2 instances
- Persistent SSD storage using EBS
- S3 object storage charges
- Storage operations
- Networking and outbound data transfer

AWS follows a pay-as-you-go pricing model where resources are billed separately. The overall pricing becomes higher when compute, storage, and networking charges are combined.

AWS also includes reservation-related upfront costs depending on the pricing option selected.

---

# 3. Azure Cost Estimation

The Azure pricing estimate was created using Azure Virtual Machines, Managed Disks, and Azure Blob Storage.

---

## Azure Services Used

| Service | Purpose |
|---|---|
| Azure Virtual Machine (B1s/B1) | Application Hosting |
| Managed Disk | VM Disk Storage |
| Azure Blob Storage | Object Storage |
| Bandwidth | Networking |

---

## Azure Linux Pricing Result

| Billing Period | Cost |
|---|---|
| Monthly Cost | $14.93 |
| Annual Cost | $179.17 |
| Upfront Cost | $0 |

---

## Azure Windows Pricing Comparison

### Windows with Azure Hybrid Benefit

| Billing Period | Cost |
|---|---|
| Monthly Cost | Similar to Linux |
| Annual Cost | Similar to Linux |

The pricing difference between Linux and Windows with Azure Hybrid Benefit was minimal because Azure allows organizations to reuse existing Windows Server licenses.

---

### Windows with License Included

| Billing Period | Cost |
|---|---|
| Monthly Cost | $16.39 |
| Annual Cost | $196.69 |

When the “License Included” option was selected, the cost increased because Azure added Windows Server licensing fees to the VM pricing.

---

## Azure Pricing Analysis

Azure pricing was significantly lower than AWS for this workload. The lower cost was influenced by:

- Lower VM pricing for the selected instance type
- Zero upfront payment
- Azure Hybrid Benefit reducing Windows licensing cost
- Competitive storage pricing

Azure demonstrated strong cost efficiency for small business workloads and Microsoft-based environments.

---

# 4. Networking Cost Comparison

Networking costs are an important factor in cloud pricing because providers charge for data transfer between services and to the public internet.

---

## AWS Networking Costs

AWS charges for:

- Outbound internet traffic
- Inter-zone data transfer
- Cross-region traffic

Inter-zone communication between resources in different availability zones increases operational cost.

---

## Azure Networking Costs

Azure also charges for:

- Outbound data transfer
- Inter-zone traffic
- Cross-region communication

However, Azure’s networking pricing for this workload remained relatively low due to the small scale of the application.

---

## Networking Analysis

For small applications, networking costs are usually manageable. However, for large-scale distributed systems, networking and data egress charges can become one of the largest cloud expenses.

Architectural decisions such as deploying resources across multiple availability zones improve reliability but also increase data transfer costs.

---

# 5. Discount Mechanisms Comparison

Both AWS and Azure provide long-term discount options to reduce cloud costs.

---

## AWS Discount Mechanisms

### AWS Savings Plans

AWS Savings Plans allow customers to commit to consistent usage over:

- 1 year
- 3 years

In exchange, AWS offers reduced pricing compared to on-demand billing.

---

### Reserved Instances

Reserved Instances provide discounts for workloads that run continuously over long periods.

Benefits include:

- Lower hourly rates
- Capacity reservation
- Predictable billing

---

## Azure Discount Mechanisms

### Azure Reserved Instances

Azure Reserved Instances reduce VM pricing when customers commit to long-term usage.

---

### Azure Hybrid Benefit

Azure Hybrid Benefit allows organizations to reuse existing Windows Server licenses on Azure. This significantly reduces the cost of Windows virtual machines.

---

## Discount Mechanism Analysis

AWS focuses heavily on usage commitment discounts through Savings Plans and Reserved Instances.

Azure provides similar reservation discounts but also adds licensing advantages for organizations already using Microsoft technologies.

This makes Azure especially attractive for:

- Windows-based businesses
- Microsoft enterprise environments

---

# 6. Final Cost Comparison

## Overall Pricing Comparison

| Provider | Monthly Cost | Annual Cost |
|---|---|
| AWS | $30.60 | $367.20 |
| Azure | $14.93 | $179.17 |

---

## Cost Difference

### Monthly Difference

```text
30.60 - 14.93 = 15.67
```

### Annual Difference

```text
367.20 - 179.17 = 188.03
```

Azure was approximately 51% cheaper than AWS for the same workload configuration.

---

# 7. Cost Optimization Strategies

## 1. Use Reserved Pricing or Savings Plans

Organizations can reduce cloud costs by committing to long-term usage through:

- AWS Savings Plans
- AWS Reserved Instances
- Azure Reserved Instances

This reduces hourly compute pricing significantly.

---

## 2. Right-Size Virtual Machines

Selecting smaller VM sizes that closely match workload requirements prevents overprovisioning and unnecessary spending.

For small web applications, lightweight instance types such as:

- t3.micro
- B1s

provide sufficient performance at lower cost.

---

# 8. Conclusion

This project demonstrated the financial and architectural differences between AWS and Azure for hosting a small web application.

The analysis showed that Azure was more cost-effective for the selected workload, with a monthly cost of $14.93 compared to AWS at $30.60.

Azure’s lower pricing was influenced by:

- Competitive VM pricing
- Zero upfront cost
- Licensing advantages through Azure Hybrid Benefit

AWS, however, remains highly flexible and widely adopted, particularly for Linux-heavy and scalable cloud-native environments.

The project also highlighted how compute resources, storage, licensing, networking, and long-term discount mechanisms all contribute to overall cloud cost.

## In Conclusion

- Azure is better suited for Microsoft-centric environments and cost-sensitive small business workloads.
- AWS remains strong for scalable, Linux-focused, and highly customizable cloud deployments.

Both platforms provide powerful infrastructure solutions, but selecting the most cost-effective provider depends on the organization’s workload requirements, licensing model, and long-term cloud strategy.