# Security and Permissions

In this section, you will understand how to configure a Lab environment in a most secure way.

First you will setup a template with the minimal permissions. Multiple template permissions can be added for each user.
Then you will add a usage policy to set alerts if the user goes above the allowed values for any resource.

Next, you will see how to configure ODL in different ways. You can configure labs to not fetch any details about the user as well.


## Restrict/Define AAD Object Actions

There are multiple ways to restrict what all actions a user or an AD SPN ( Service Principal ) can perform in Azure using CloudLabs

### Assign a Built-in Role to AAD Objects (User/SPN)

AAD Objects can be assigned Reader/Contributor/Owner/Storage Blob Data Owner role at Resource Group or Subscription scopes. 

  - **Reader** can view and access Azure resources
  - **Contributor** can create and manage all types of Azure resources but can't grant access to others.
  - **Owner** can create and manage all types of Azure resources as well as grant access to others.
  - **Storage Blob Data Owner** has full access to Azure Storage blob containers and data, including assigning POSIX access control
  
 > Note: We prefer providing only Reader permission for the user by default. Actions that can be performed can be mentioned in the Custom Role and assigned to the User/SPN

### Assign a Custom Role to AAD Objects ( User/SPN )

If the built-in roles in CloudLabs don't meet the specific needs for the workshops or you want to provide only specific actions for each user, you can create your own custom roles. 

Just like built-in roles, you can assign custom roles to users and service principals on top of the built-in role that is defined at subscription, and resource group scopes.

Custom Role definition is given here: https://docs.microsoft.com/en-us/azure/role-based-access-control/custom-roles#custom-role-example 

The custom roles will be saved as a Json File and uploaded to a public storage solution. Then this URL is provided while configuring the Custom Role permission in CloudLabs.
