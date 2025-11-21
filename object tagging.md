It is a schema level object to assign specific metadata to other database objects. 
It serves as a label or a classification mechanism.

objects can be assigned to a tag during or after it has been created.

This helps with #DATA_GOVERNANCE!

Data Governance: best practice and principles for organizing, securing and data compliance.

List of Data Governance:
- Data Quality Monitoring
- Data Sensitivity and Access Visibility
	- Object Tagging
	- Sensitive Data Classification.
- Data Access Policies
	- Masking Policies
	- Row access policies
- Data lineage and Dependancies.

We can tag an object with an object tag and whatever policies were assigned to that tag, the policies are also attached to said objects.

Data Steward: is a team or user responsible for data Governance strategies.

***CREATE A TAG:***
	CREATE OR REPLACE TAG business_unit allowed_values 'sales','HR','operations';
**SHOW ALL TAGS VALUES ACCEPTED**:
	SELECT ==system$get_tag_allowed_values==('security_objects_db.security_objects_schema.business_unit');
**ADD A TAG VALUE**
	ALTER TAG security_objects_db.security_objects_schema.business_unit ADD ALLOWED_VALUES 'engineering'; 

We add upto 50 tags on an object.