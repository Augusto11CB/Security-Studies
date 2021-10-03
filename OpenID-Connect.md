# OpenID Connect 

## Summary
- OpenID Connect is built on top of OAuth 2.0 as an additional identity layer. It uses the concept of an ID token. An ID token is a JWT that contains authenticated user information, including user claims and other relevant attributes.

- When an authorization server issues an ID token, it signs the contents of the JWT (a signed JWT is called a JWS, or JSON Web Signature), using its private key. 

- Before any application accepts an ID token as valid, it should verify its contents by validating the signature of the JWT.

### ID Token vs Access Token
- An **ID token** is consumed by an application to get information, such as a user’s username, email address, phone number 
- An **access token** is a credential used by an application to access a secured API on behalf of an end user or just by being itself.
- **OAuth 2.0 provides only an access token**, whereas **OpenID Connect provides both** an access token and an ID token.

### Example Decoded ID token (Payload)

```json
{
   "iss":"http://server.example.com",
   "sub":"janedoe@example.xom",
   "aud":"8ajduw82swiw",
   "nonce":"82jd27djuw72jduw92ksury",
   "exp":1311281970,
   "iat":1311280970,
   "auth_time":1539339705,
   "acr":"urn:mace:incommon:iap:silver",
   "amr":"password",
   "azp":"8ajduw82swiw"
}
```

- iss: The identifier of the issuer of the ID token (usually, an identifier to represent the authorization server that issued the ID token).

- sub: The subject of the token for which the token was issued (usually, the user who authenticated at the authorization server).

- aud: The audience of the token; a collection of identifiers of entities that are supposed to use the token for a particular purpose. It must contain the OAuth 2.0 client_id of the client application, and zero or more other identifiers (an array). If a particular client application uses an ID token, it should validate whether it’s one of the intended audiences of the ID token; the client application’s client_id should be one of the values in the aud claim.

- iat: The time at which the ID token was issued.

- exp: The time at which the ID token expires. An application must use an ID token only if its exp claim is later than the current timestamp.