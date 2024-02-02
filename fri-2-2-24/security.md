## Security

Security should always be a priority when working in production environments when people's real data will be stored. We'll take a look at some services that help manage access to data/services/secrets. 

### IAM - Identity Access Management
Framework of policies and technologies that people can only access what they should have access to. For example, an intern shouldn't be able to change people's salaries. Not everyone should be able to control/allocate new resources. People who are working with databases might not need to create a VM. 

Least-Privileged Access - We don't want to give any unnecessary permissions to people. They should be granted access to features/data/services that they need to complete their job. 

### Microsoft Entra ID (Formerly: Azure AD (Active Directory))

Despite the name change, the functionality remains the same. The service lets you manage identities and what they access in your application/services/data. Authenticate and authorize users. 

SSO - Single Sign On - With a single sign-in, can access many things in your company's domain.

MFA - Multi-Factor Authentication - Multiple ways of verifying who you are. One example of this is even after you log in with username/password, you need a code that is only sent to a certain device. 

Can manage users, groups, and roles

#### Authenticate
Ensuring that you are who you say you are.

#### Authorize
Dictating what you are allowed to access.

### Active Directory Federation Services (ADFS)
Provide SSO and MFA for applications. The part of this service that differentiates itself from Entra ID is that it can deal with private cloud/on-premise infrastructures and can even bridge the gap between 2 companies. 

If 2 companies want to interact with one another's services/data, can use the ADFS to act as a middleman between them to ensure authentication and authorization. 

### Azure Key Vault

A service that lets us store keys, certificates, and secrets in such a way that we have a lot of control over who can access this data. 

- Examples of things we can store:
  - Password to database
  - User Token/Certificate to authenticate a user
  - Web App Github Actions file used secrets

When we deployed our web app, we saw that secrets were used to store Azure-specific keys that are necessary to bridge the gap between Github repo and the Azure account in order to deploy the web app. But, we obviously wouldn't want to store these items publicly, so secrets are used, and they're configured so that only the specified Azure Services can see them. 




## Resources
- [Identity Management Overview](https://learn.microsoft.com/en-us/azure/security/fundamentals/identity-management-overview)
- [Microsoft Entra Id](https://learn.microsoft.com/en-us/entra/fundamentals/whatis)
- [ADFS](https://learn.microsoft.com/en-us/windows-server/identity/ad-fs/ad-fs-overview)
- [Good Video on ADFS](https://www.youtube.com/watch?v=WUax8vTkoKQ)
- [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/general/basic-concepts)