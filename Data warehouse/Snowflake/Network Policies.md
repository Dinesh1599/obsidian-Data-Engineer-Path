To create a Network policy Do the following

1. **Create a Network Rule**

CREATE NETWORK RULE "rule_name"
	Mode = INGRESS
	TYPE = IPv4
	VALUE_LIST = ("MENTION ALL ip here");

Note: It does not support IPv6

2. **Create a network policy and assign the rule**

CREATE NETWORK POLICY "policy name"
ALLOWED_NETWORK_RULE_LIST = ('rule name')
BLOCKED_NETWORK_RULE_LIST = ('rule_name')

Note: 
1. All IP addresses outside the allow list will be denied access
2. priority to blocked rule list is given if ip is on both allow and block rule list

3.  **Assign network policy to the account**

	ALTER ACCOUNT "account_name" SET NETWORK POLICY "np name "


Note: 
1. only 1 network policy per account per user.
2. To bypass network_policy: use MINS_TO_BYPASS_NETWORK_POLICY
3. If a User has network policy on both account and user level, user level takes precedence.

Roles that can create policy and rules
1. ACCOUNTADMIN
2. SECURITYADMIN
3. ROLES with CREATE NETWORK POLICY AND CREATE NETWORK RULE.