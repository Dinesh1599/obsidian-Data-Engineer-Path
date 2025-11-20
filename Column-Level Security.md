Dynamic Data Masking:
Security Policy where a Security feature is placed on a column in a table or view at ==query run time.==

To create a policy (Masking Policy):

==CREATE MASKING POLICY==  email_mask as (VAL string) returns string ->
CASE
WHEN CURRENT_ROLE() IN ('SUPPORT') THEN VAL
ELSE "########"
END;
