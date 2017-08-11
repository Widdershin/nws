# nws
Nick's Web Services - in which I foolishly attempt to build a replacement for AWS

## Philosophy

* Infrastructure is to be represented as code, and that code shall be checked into version control
* Modifications to provisioned infrastructure are performed by atomic changesets
* Modifying code, generating and applying changesets are the only way to modify infrastructure
* Any GUI that modifies infrastructure will only produce a changeset that needs to be integrated into the code to be applied
* No resource shall be destroyed unnecessarily. Renaming a resource should not require destroying and recreating.

That might sound a lot like Terraform with AWS, but Terraform plans are not atomic. You often need to replan and reapply in order to succesfully complete a deploy. Additionally AWS encourages use of the UI over CloudFormation and Terraform. While CloudFormation has ample documentation, the normal AWS documentation details the use of the UI to provision infrastrcture.

I don't think is Terraform's fault, but instead I feel that this is a result of AWS not being originally designed with these criteria in mind. Terraform is attempting to create a declarative API on top of an imperative API that wasn't designed for it, and it shows.

## Plan

Investigate existing alternatives to AWS. Do any of them satisfy the above criteria? If so, great.

Mikey suggests:

https://saltstack.com/
https://www.terraform.io/ (perhaps with another provider than AWS)
https://kubernetes.io/
http://rancher.com/
https://wiki.openstack.org/wiki/Heat 
