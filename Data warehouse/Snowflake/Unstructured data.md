They are data like
	Video files
	Audio files
	documents

Snowflake supports:
1. Access files through URL from external cloud storage
2. Share files access via URLs


Types of URLs that snowflake provides:
1. Scoped URLs
	1. Encoded url with temporary access to a file with no access to the stage itself
	2. default 24hrs - with the result cache expires
	3. returned by calling ==BUILD_SCOPED_FILE_URL==
2. File URL
	1. The url that doesnt expire
	2. returned by calling ==BUILD_STAGE_FILE_URL==
3. Pre-signed url
	1. HTTPS url to access a file via the web browser.
	2. Expiration time can be configured here.
	3. returned by calling ==GET_PRESIGNED_URL==

Example syntax:
	SELECT BUILD_SCOPED_FILE_URL (@external_stage,'logo.png')