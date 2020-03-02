# Debugging SAML and GHES

## General debugging

Most of the SAML data is filter from the logs but we do provide a “SAML debug” option within the Admin Center, enabling this will allow you to see the “raw” SAMLRequest and SAMLResponse data. Log files are located at `/var/log/github/`.

## External authentication returned an invalid message

```
SAMLResponse failed validation (check required attributes and Signing)
External authentication has denied your request to access this site
SAMLResponse includes `urn:oasis:names:tc:SAML:2.0:status:RequestDenied`
External authentication was not able to authenticate you
SAMLResponse != `urn:oasis:names:tc:SAML:2.0:status:Success` or not included
```

Potential causes:
- Issuer in SAMLResponse doesn’t match setting in Management Console (or is empty)
- Destination in the SAML response was not valid.
- Recipient in the SAML response must not be blank.
- Destination attribute doesn’t match GHES

Helpful resource: [Supported SAML attributes](https://help.github.com/en/enterprise/admin/user-management/using-saml#saml-attributes)

## Digest mismatch

```
Signature was unable to be deciphered
```

Potential causes:
- Wrong IdP certificate was uploaded or SAMLResponse signed with different cert
- Wrong Sig-Alg configured in Management Console
- Audience invalid
- Audience attribute sent by IdP is not correct
- Current time is earlier than NotBefore condition
- Current time is on or after NotOnOrAfter condition

Helpful resource: [Supported SAML attributes](https://help.github.com/en/enterprise/admin/user-management/using-saml#saml-attributes)

## Another user already owns the email

Potential causes:
- User not found in SAML mapping table nor was a legacy user (without SAML mapping) found, tried to create new user + mapping but email is owned by another user

## Another user already owns the account

Potential causes:
- User not found in SAML mapping table, legacy user was found but already has an entry in the SAML mapping table

## Cannot authenticate as an Organization

Potential causes:
- “User” found but is actually an organization