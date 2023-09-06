# OpenSSL - Validating Certificate Against CRL

To verify a certificate against a CRL (in this case a file), the CRL file must contain the full chain of CRLs from the lowest intermediate CA to the highest CA (CA Root). If all the chain is not provided, there will be an error similar to this: `error 3 at 1 depth lookup: unable to get certificate CRL` (see discution in this Stackoverflow: [Verifying a certificate against a CRL via OpenSSL: Unable to get certificate CRL](https://stackoverflow.com/questions/45847531/verifying-a-certificate-against-a-crl-via-openssl-unable-to-get-certificate-crl)).



### Reference

* [Documentation OpenSSL `verify`  Command](https://www.openssl.org/docs/man1.1.1/man1/openssl-verify.html)
