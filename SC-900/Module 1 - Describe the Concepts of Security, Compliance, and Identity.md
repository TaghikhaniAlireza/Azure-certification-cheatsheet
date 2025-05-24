# Shared Responsibility Model
- Identifies which security tasks are handled by the cloud provider, and which security tasks are handled by you, the customer.
- **On-premises datacenters**: In an on-premises datacenter, you have responsibility for everything from physical security to encrypting sensitive data.
- **Infrastructure as a Service (IaaS)**: Of all cloud services, IaaS requires the most management by the cloud customer. The cloud customer isn't responsible for the physical components, such as computers, the network, or the physical security of the datacenter.
- **Platform as a Service (PaaS)**: The cloud provider manages the hardware and operating systems, and the customer is responsible for applications and data.
- **Software as a Service (SaaS)**: SaaS requires the least amount of management by the cloud customer. The cloud provider is responsible for managing everything except data, devices, accounts, and identities.
- **In summary**, responsibilities always retained by the customer organization include:
  - Information and data  
  - Devices (mobile and PCs)  
  - Accounts and identities
  - ![shared-responsibility-model](../images/SC-900/3-shared-responsibility-model.png)

# Defense in Depth
- Uses a layered approach to security, rather than relying on a single perimeter.
- Layers of security might include:
  - **Physical security** such as limiting access to a datacenter to only authorized personnel.
  - **Identity and access security controls**, such as multifactor authentication or condition-based access, to control access to infrastructure and change control.
  - **Perimeter security** of your corporate network includes distributed denial of service (DDoS) protection.
  - **Network security**, such as network segmentation and network access controls.
  - **Compute layer security**, securing access to virtual machines by closing certain ports.
  - **Application layer security** to ensure applications are secure and free of vulnerabilities.
  - **Data layer security**, including access controls and encryption.

## Confidentiality, Integrity, Availability (CIA)
- **Confidentiality**: Keep sensitive data (e.g., customer info, passwords) confidential.
- **Integrity**: Ensure data hasn't been altered or tampered with.
- **Availability**: Ensure data is accessible when needed.

# Zero Trust Model
- Assumes everything is on an open and untrusted network.
- Operates on the principle of “trust no one, verify everything.”

## In practice
- No longer assume passwords are sufficient.
- Use multi-factor authentication for additional checks.

## Zero Trust Guiding Principles
- **Verify explicitly**: Authenticate and authorize based on identity, location, device, data, etc.
- **Least privileged access**: Limit access with JIT/JEA, risk-based policies, data protection.
- **Assume breach**: Segment access, use encryption, analytics, and monitoring.

## Six Foundational Pillars
- **Identities**: Must be verified with strong authentication and least privilege access.
- **Devices**: Monitor device health and compliance.
- **Applications**: Discover and manage all applications including Shadow IT.
- **Data**: Classify, label, and encrypt. Protect data across its lifecycle.
- **Infrastructure**: Assess versions/configs, use JIT access, and detect anomalies.
- **Networks**: Use microsegmentation, real-time threat protection, encryption, and analytics.

![zero-trust-pillars-v2](../images/SC-900/2-zero-trust-pillars-v2.png)

# Encryption and Hashing

## Encryption
- Makes data unreadable to unauthorized users.
- **Symmetric encryption**: Same key for encryption and decryption.
- **Asymmetric encryption**: Uses a public/private key pair.

### Encryption Types
- **Data at rest**: Stored data on servers, databases; needs encryption.
- **Data in transit**: Data moving across networks; needs encryption.
- **Data in use**: Data in RAM or CPU cache; may be encrypted.

## Hashing
- Converts text to a unique fixed-length value (hash) using algorithms.

# Governance, Risk, and Compliance (GRC)

## Framework
- Implement policies, processes, and technologies.

## Governance
- System of rules, practices, and processes for directing the organization.

## Risk
- Identifying, assessing, and responding to threats to objectives.

## Compliance
- Meeting legal/regulatory standards based on location.

### Compliance Considerations
- **Data residency**: Where data is stored and processed.
- **Data sovereignty**: Data subject to local jurisdiction laws.
- **Data privacy**: Transparency in collecting, processing, and sharing data.
- ![grc-framework-v3-inline](../images/SC-900/grc-framework-v3-inline.png)
