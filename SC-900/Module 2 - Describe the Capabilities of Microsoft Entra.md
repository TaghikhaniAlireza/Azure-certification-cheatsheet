## Basic Concept

- formerly Azure Active Directory, is Microsoft’s cloud-based identity and access management service.
- Organizations use Microsoft Entra ID to:
  - Internal resources, such as apps on your corporate network and intranet, and cloud apps developed by your own organization.
  - External services, such as Microsoft Office 365, the Azure portal, and any SaaS applications used by your organization.
- Microsoft Entra ID also allows organizations to securely enable the use of personal devices, such as mobiles and tablets, and enable collaboration with business partners and customers.

- **Identity Secure Score**: which is a percentage that functions as an indicator for how aligned you are with Microsoft's best practice recommendations for security.
  - Each improvement action in identity secure score is tailored to your specific configuration.
  - Helps you to objectively measure your identity security posture, plan identity security improvements, and review the success of your improvements.
  - ![entra-id-general-diagram-v2](../images/SC-900/entra-id-general-diagram-v2.png)

- **Basic terminology:**
  - **Tenant**: A Microsoft Entra tenant is an instance of Microsoft Entra ID in which information about a single organization resides including organizational objects such as users, groups, devices, and application registrations.
    - A tenant also contains access and compliance policies for resources, such as applications registered in the directory.
    - Each Microsoft Entra tenant has a unique ID (tenant ID) and a domain name.
  - **Directory**: The directory is a logical container within a Microsoft Entra tenant that holds and organizes the various resources and objects related to identity and access management including users, groups, applications, devices, and other directory objects.
    - The directory is like a database or catalog of identities and resources associated with an organization's tenant.
    - A Microsoft Entra tenant consists of only one directory.
  - **Multi-tenant**: Is an organization that has more than one instance of Microsoft Entra ID.
    - Organizations with multiple subsidiaries or business units that operate independently.
    - Organizations that merge or acquire companies.
    - Multiple geographical boundaries with various residency regulations.

- **Who uses Microsoft Entra ID?**
  - Used by IT admins to control access to corporate apps and resources, based on business requirements.
  - Microsoft Entra ID can also be set up to require multi-factor authentication when accessing important organizational resources.
  - Developers use Microsoft Entra ID as a standards-based approach for adding single sign-on (SSO) to their apps.
  - Microsoft Entra ID also provides application programming interfaces (APIs) that allow developers to build personalized app experiences using existing organizational data.

> Subscribers to Azure services, Microsoft 365, or Dynamics 365 automatically have access to Microsoft Entra ID.

