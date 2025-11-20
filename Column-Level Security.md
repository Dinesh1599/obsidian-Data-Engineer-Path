Dynamic Data Masking:
Security Policy where a Security feature is placed on a column in a table or view at ==query run time.==

To create a policy (Masking Policy):

==CREATE MASKING POLICY==  email_mask as (VAL string) returns string ->
CASE
WHEN CURRENT_ROLE() IN ('SUPPORT') THEN VAL
ELSE "########"
END;

Options:
![[Pasted image 20251120152011.png]]

To add the policy:
ALTER TABLE IF EXISTS emp_info MODIFY COLUMN USER_EMAIL SET MASKING POLICY EMAIL_MASK;


1. Masking policies are schema level objects
2. creating these policies are done independently of object owners.
3. masking policies can be nested in tables and views.
4. A masking policy is applied no matter where the column is referenced.
5. A masking policy can be applied to an object even before or after its been created.

 Masking policies can use external functions to mask their data - EXTERNAL TOKENIZATION.
	 In this case the data is not dynamically tokenized, but instead the data stored in the column itself is encrypted.
![[Pasted image 20251120152549.png]]

