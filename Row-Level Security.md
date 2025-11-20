This is the security policy which enables which rows are to be returned in a query.

Sytax:

CREATE OR REPLACE ROW_ACCESS_POLICY RAP_ID AS (ACC_ID VARCHAR) RETURNS BOOLEAN ->
WHEN 'ADMIN' = CURRENT_ROLE() THEN TRUE
ELSE FALSE
END;

To add the policy:
ALTER TABLE ACCOUNTS ADD ROW ACCESS POLICY RAP_ID on (ACC_ID)

1. They are schema level objects
2. Segregation of duties
3. Nested policies
4. Creation and applying workflow.

Note: 
1. Adding a column level policy on to a column referenced on a row access policy, it fails.
2. row access policies are evaluated before data masking policies.