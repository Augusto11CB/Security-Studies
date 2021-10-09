# What Every Developer Must Know About HTTPS

## HTTPS
HTTPS is the HTTP procotol running over TLS, in other words is the secured version of HTTP. By using HTTPS every packet transferred between client and server is encrypted using public or private key cryptography.

## Concept Man in the Middle Attacks (MitM)
- In cryptography and computer security, a man-in-the-middle attack is a cyberattack where the attacker secretly relays and possibly alters the communications between two parties who believe that they are directly communicating with each other, as the attacker has inserted themselves between the two parties.


## What does HTTPS give you?
- **Confidentiality**: All the traffic between the client and the server is encrypted, preventing anyone from understanding it even if they can intercept it.

- **Integrity**:  Integrity checks ensure that the messages making up the HTTP traffic **cannot be altered** in transit, neither can messages be added or removed from the sequence, without detection.

- **Authenticity**: Simply providing encryption and message integrity gives little security if you do not know who the other party in the conversation actually is. Under HTTPS, all servers offer the browser a cryptographic "certificate". These certificates are issued by trusted third parties and contain information that identifies the server and the organisation operating it. 

## CA - Certification Authority
How to make sure that the party we are talking to is actually who they claim they are? This is where the certificate authority comes in.

A certificate authority (CA) is a third-party organization with 3 main **objectives**.
1. Issuing Certificates
2. Confirming the identity of the certificate owner
3. Provide proof that the certificate is valid

### Digital Certificate
- A digital certificate certifies the ownership of a public key by the named subject of the certificate

## SSL and TLS
Both TLS (Transport Layer Security) and SSL (Secure Sockets Layer) are cryptographic protocols that provide security over a network. The TLS is the evolution (the most updated version) of SSL which now is deprecated since 2015 by the IETF (Internet Engineering Task Force).

### The TLS Handshake
The **process to established a secure connection** to transmit messages is called **handshake**. Here some agreements are made in order to determine how to communicate securely.

1. The client send a list of SSL/TLS  versions and encryption algorithms (**Cypher Suite**) that it can works. 
2. The server choose the best SSL/TLS version and encryption algorithm and reply with its certificate which includes public key, so they can verify the server identity.
3. Client verifies the received certificate against a CA using it's public key. If the validation is consistent, the client generates a "pre master key" that is encrypted by the server public key. In the end the client send a request to the server with the generated content.
4. The server decrypt the "pre master key".
5. Both server and client have generated the same "shared secret" that they are going to use as a symmetric key

## TLS and HTTPS Acronyms
- SNI
    - Server name indication
    - Enables multiple certs on the one IP address
- SAN
    - Subject Alternative Name
    - Combine multiple domain names on the one cert
- PFS
    - Perfect Forward Secrecy
    - Protects past sessions against future key compromise
- DNSSEC
    - Domain Name System Security Extensions
    - Protects against forged DNS records
- DANE
    - DNS Based Authentication of Named Entities
    - Specifies the cert keys at the DNS level
- CAA
    - Certificate Authority Authorization
    - Specifies allowable CAs for the domain at the DNS level
- CRL
    - Certificate Revocation List
    - List of revoked certificates maintained by the CA
- OCSP
    - Online Certificate Status Protocol
    - List of revoked certificates maintained by the CA
- PKP
    - Public Key Pinning
    - Ensures a client will only accept predefined certs

## Cool Websites
- https://badssl.com/
- https://www.ssllabs.com/ssltest/
- [How to generate a self-signed SSL certificate using OpenSSL](https://stackoverflow.com/questions/10175812/how-to-generate-a-self-signed-ssl-certificate-using-openssl)

## Reference
- [Web Server Management: Securing Access to Web Servers - University of Cambridge Computing Service](https://www.cl.cam.ac.uk/~jw35/courses/using_https/html/book1.htm)