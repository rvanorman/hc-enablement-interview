layout: true
class: compact
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s6-dynamic-secrets-setup-3

## Creating and Revoking the Dynamic Secrets

- Using the following commands in Vault you can generate a user in AWS with the policy added to my-role earlier as well as revoke the user in the event it needs to be revoked before the lease expires.

```
user@host:~$ vault read aws/creds/my-role
Key                Value
---                -----
lease_id           aws/creds/my-role/YHqWlOOSOcN5YlF4a6kXQV3o
...
user@host:~$ vault lease revoke aws/creds/my-role/YHqWlOOSOcN5YlF4a6kXQV3o
All revocation operations queued successfully!
```

???
6) Now you can generate a user with access to your AWS account for 32 days or until revoked

vault read aws/creds/my-role

7) Check out in AWS to see the new user created (may need to refresh the page for it to show in IAM)

8) Revoke the user early if needed

vault lease revoke aws/creds/my-role/<your-lease-id>

---
