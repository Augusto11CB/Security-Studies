# Server Name Indication (SNI)

* SNI solves the problem of loading multiple SSL certificates onto one web server (to serve multiple websites).
* It’s a “newer” protocol, and requires the client to indicate the hostname of the target server in the initial SSL handshake.
* The server will then find the correct certificate, or return the default one.

### References

MAAREK, Stephane_. Ultimate AWS Certified Developer Associate 2023 NEW DVA-C02._ \[Videoaula]. Udemy. Disponível em: [https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/](https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/). Acesso em: 9 set. 2023.&#x20;

