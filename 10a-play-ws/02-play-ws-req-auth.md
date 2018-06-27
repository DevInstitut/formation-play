# Requête avec authentification

```java
// requête avec authentification BASIC
// options possibles : BASIC, DIGEST, KERBEROS, NTLM, and SPNEGO.
ws.url(url).setAuth("user", "password", WSAuthScheme.BASIC).get();

// suivre les redirections
ws.url(url).setFollowRedirects(true).get();

// définir des paramètres de requêtes
ws.url(url).setQueryParameter("paramKey", "paramValue");


// définir un timeout
ws.url(url).setRequestTimeout(1000).get();
```
