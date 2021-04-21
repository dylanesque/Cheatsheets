# IAM

+ IAM is the Identity Access Management portion of AWS

+ A User is an end-user, such as an employee.

+ A Group is a collection of Users

+ A Role is a created classification assigned in AWS Resources

+ Policies are JSON documents that contain information about what privileges a User/Group/Role has.

+ IAM is universal, and doesn't apply to regions at the time of this writing.

+ When one first sets up their AWS account, a root account with full admin access is automatically created.

+ New Users have NO permissions when first created

+ New Users can be assigned Access Key ID & Secret Access Keys when first created for acces to the CLI, SDK, and other dev tools, and a password for access to the mgmt console

+ Save these values in a secure location; you can only view them once, and will have to regenerate them if lost.

+ Always set Multifactor Authentication on your account.

+ Policies are documents that define sets of permissions
  
+ All permissions are implicitly denied until set to otherwise

+ You can customize password requirements using IAM.

+ Billing alarms can be created to warn of costs going over a certain amount.