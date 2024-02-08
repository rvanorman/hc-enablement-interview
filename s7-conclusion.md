layout: true
class: img-right
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s7-conclusion

## Wrapping Up: Why Use Dynamic Secrets with AWS?

![scale:75%](./assets/images/aws-images/User_Created_from_Vault.png)

- ![:fontsize 75%](Notice that everytime you run 'vault read aws/creds/my-role' a new user is created inside of AWS, using the policy associated to my-role in Vault.)
- ![:fontsize 75%](Using dynamic secrets could be used for purposes of automation in a script to create a user on demand, build an instance, and then revoke the user afterwards.)
- ![:fontsize 75%](Another use case could be to utilize Vault itself to govern access to AWS, enforcing desired rotation of creditials to your AWS accounts.)

???
There are many other reasons that one could come up with to utilize Vault's dynamic secrets with AWS, this was just a showcase of how to deploy and implement dynamic secrets into AWS. The world is yours!

