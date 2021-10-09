# Securing Data with Asymmetric Cryptography
- CA    
    - Certificate Authority
        - as an organization
            - Verisign or Entrust
        - as an implementation on a machine
            - Root Certificate authorities, intermediate certificate authorities and policy certificate authorities
    - Certification Authority

- Public Key infractructure (PKI)
    - For Responsibilities of a PKI
        - Authentication
        - Integrity
        - Confidentiality (encryption)
        - Non-Repudiation

### Root CA
- The root CA is at the top of the hierarchy and there is only one instance of it
- It signs certificates for the next tier of CA instances
    - These CAs, in turn, might sign end user certs or they might sign certificates for CAs at the next tier down
- Root CA Certificate is self signed
- Basic Constraits extension

### Types of Certificate Authorities
- Root Certificate Authority
- Intermediate Certificate Authority
- Policy Certificate Authority

### Why do we have a CA hierarchy ?
- Organization
    -  Provides separation of concerns both tecnologically and geographically
- Risk Mitigation
    - Dividing authorities by responsibilities and geography limits damanage in the case of a breach or a CA is compromised in some fashon

### Trust CA
- How much trust to put in it?
- What lenghts do CA go to ensure identity?
- What sort of trust criteria should we know about certificate authorities?
    - Certificate Practice Statement
        - A statement of the practices that a certification authority employs in issuing, suspending, revoking, and renewing certificates and providing access to them, in accordance with specific requirements (i.e., requirements specified in this certificate policy, or requirements specified in a contract for services).
        - Issuance criteria
        - Revocation Criteria
        - Renewal Criteria
   
### Encryption/Decryption
- Encrypt data with the public key
- Decrypt data with the private key

### Signing/Validation
- Sign data with the private key
- verify the signature with the public key

### Verifying a Certificate
- OCSP Online certificate Status Protocol
- The OCSP's URL can be found in the "Authority Information Access" certificate extesion


### Key Pair

#### What is the Difference between symmetric and asymmetric cryptography?
- Symmetric cryptography both sides use the same key to do the encryption and decryption of the data
- Asymmetric cryptography, we have two type of keys, the first is the public key and the second is the private key.
    - Encrypt data with the public key
    - Decrypt data with the private key

### PKI Certificate Types
- Certificate Request
- Certificate
- Certificate Revocation List

### The Certificate Structure - X.509 Certificate
- Trust comes from third-party validation of information

### Fields
- Version
- Serial number
    - Unique identifier within a certification authority
- Signature algorithm
    - SHA is the preffered algorithm
    - Used in conjunction with a PKI encryption algorithm
- Issuer
    - Distinguished Name
        - C=US, O=My Airlines, OU=Security, CN=Certification Authority
- Subject
    - Distinguished Name
        - C=US, O=My Airlines, OU=Operations, CN=Ducky Mallard
- Public Key
- Extensions
    - Used to define specific purpose(s) of a certificate
    - We can add our own extensions to a certificate if needed

### Certificate Signature Request - How to validate a certificate?
- The certificate type that is used provide the public key and associated information to a certification authority for validation and signature

#### Structure of Certificate Signature Request
- Version
- Subject
    - Distinguished Name
        - C=US, O=My Airlines, OU=Operations, CN=Ducky Mallard
- Public key
- Extensions
    - Used to define specific purpose(s) of a certificate
    - We can add our own extensions to a certificate if needed