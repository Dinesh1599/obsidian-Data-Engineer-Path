1. Roles are entity where privileges on objects are given
2. Roles are then assigned users
3. Users can have multiple roles
4. There can be a hierarchy in roles. 
5.  Privileges of child roles are inherited from the parent
![[Pasted image 20251119184548.png]]


Default Roles (In order of privileges DESC)

1. ORGADMIN
2. ACCOUNTADMIN
3. SECURITY AND SYSADMIN
4. USERADMIN
5. PUBLIC
![[Pasted image 20251119184901.png]]![[Pasted image 20251119185011.png]]

Custom Roles:
	They are roles with custom privileges for security
	This is good for security privileges. Security principle of least privilege.

Recommended: Creating a hierarchy of custom roles with top-most custom role assigned to the sysadmin. if not assigned. SYSADMINs will not be able to manage objects owned by custom roles.


Important Queries:

SHOW GRANTS OF ROLE <roleName>   -- shows all users and roles that have been granted the role
SHOW GRANTS TO ROLE <roleName>   -- shows privileges the role has on objects  