UDF that are stored and executed outside of snowflake

Basically snowflake codes that are executed **outside** snowflake

1. No code is stored in the function definition
2. Reference third-party libraries, services and data
3. Snowflake stores security-related external function information in an [[API integration]].
4. Remotely executed code is called as **remote service**
5. It is a schema level object

Query:

CREATE external function az_func(string_col VARCHAR)
returns variant
api_integration = azure_external_api_integration
as ''<provider_link>"


API Integration:

An _integration_ is a Snowflake object that provides an interface between Snowflake and third-party services. An API integration stores information, such as security information, that is needed to work with a proxy service or remote service.

Limitation:
	Must be scalar
	There is some overhead + fewer optimization.
	Not Sharable

My Understanding:
	External functions let Snowflake run your outside code or APIs directly from SQL queries.
	Remote Service: the place where your external function’s real code lives.

External function Lifecycle:
	![[Pasted image 20251117201055.png]]