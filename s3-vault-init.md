layout: true
class: compact
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s3-vault-init

## Initializing the Vault Cluster

Now we initialize Vault and set up autopilot. Save your recovery keys in a secure fashion! SSH to one of the Vault instances and run the following in order:

```
user@host:~$ vault operator init
...
Success! Vault is initialized
user@host:~$ export VAULT_TOKEN="<your Vault token>"
user@host:~$ vault operator raft list-peers
Node                   Address            State       Voter
----                   -------            -----       -----
i-042c1138b7bb9af97    10.7.3.244:8201    leader      true
...
i-08261c9ee1d431a20    10.7.5.136:8201    follower    true
user@host:~$ vault operator raft autopilot set-config -cleanup-dead-servers=true -dead-server-last-contact-threshold=10 -min-quorum=3
```

???

---
