Data is Encrypted at AES-256
Data is always encrypted at rest.
Encryption on transit encrypted with TLS 1.2

E2EE flow:

Uses Hierarchical key model
![[Pasted image 20251120141007.png]]

Root Key:
1. Snowflake uses AWS CloudHSM to create and protect the root key
2. Generates lower level keys

Key Rotation:
Replacing existing accounts and table encrpytion keys every 30 days.

Re-keying:
 Once a retired key exceeds 1yr, Snowflake automatically creates a new encryption key and re-encrypts all data previously protected by the retired key using the new key.