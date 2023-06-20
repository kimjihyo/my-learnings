# OAuth

OAuth is an open-standard authorization protocol or framework that provides applications the ability for "secure designated access". OAuth doesn't share password data but instead uses authorization tokens to prove an identity between consumers and service providers. OAuth is an authorization protocol that allows you to approve one application with another on your behalf without giving away your password.



## OAuth 1.0

The OAuth protocol was stablized at version 1.0 in October 2007, and revised in June 2009 (Revision A) as published at https://oauth.net/core/1.0a/.

### Roles

**Service Provider**\
A web application that allows access via OAuth.

**User**\
An individual who has an account with the Serivce Provider

**Consumer**\
A website or application that uses OAuth to access the Service Provider on behalf of the User.

**Consumer Key**\
A value used by the Consumer to identify itself to the Service Provider.

**Consumer Secret**\
A secret used by the Consumer to establish ownership of the Consumer Key.

**Request Token**\
A value used by the Consumer to obtain authorization from the User, and exchanged for an Access Token.

**Access Token**\
A value used by the Consumer to gain access to the Protected Resoures on behalf of the User, instead of using the User's Service Provider credentials.

**Token Secret**\
A secret used by the Consumer to establish ownership of a given Token.


## OAuth 2.0
The OAuth 2.0 authorization framework enables a third-partiy application to obtain limited access to an HTTP service, either on behalf of a resource owener by orchestarting an approvall interaction between the resource owner and the HTTP service, oor by allowing the third-party application to obtain access on its own behalf. This specifiaction replaces and obsoletes the OAuth 1.0 protocol described in RFC 5849.

### Roles

**Resource Owner**\
An entity capable of granting access to a protected resource. When the resource owner is a persionm it is referred to as an end-user.

**Resource Server**\
The server hosting the protected resources, capable of accepting and responing to protected resource requests using access tokens.

**Client**\
Ap application making protected resource requests on behalf of the resource owner and with its authorization. The term "client" does not imply and particular implementation characteristics.

**Authorization Server**\
The serer issuing access tokens to the client after successfully authenticating the resource owner and obtaining authorization.

### Flow

![oauth2.0_flow_1](./oath2.0_flow_1.png)

- (A) The client requests authorization from the resource owner. The authroization request can be made directly to the resource owner, or preferably indirectly via the authorization server as an intermediary.

- (B) The client receives an authorization grant, which is a credential representing the resource owner's authorization, expressed using one of four grant types defined in this specifiation or using an extension grant type.

- (C) The client request an access token by authenticating with the authorization server and presenting the authorization grant.

- (D) The authorization server authenticates the client and validates the authorization grant, and if valid, issues an access token.

- (E) The client requests the protected resource from the resource server and authenticates by presenting the access token.

- (F) The resource server validates the access token, and if valid, serves the request.

### Authorization Grant

An authorization grant is a credential representing the resource owner's authorization used by the client to obtain an access token. There are four grant types -- authorization code, implicit, resource owner password credentials, and client credentials.

## Differences between Oauth 1.0 and OAuth 2.0

Followings are the major improvements that has happened in OAuth2.0

- Better support for non-browser applications 
- Reduced complexity in signing requests
- The separation of roles
- The short-ived access token and the refresh token.
