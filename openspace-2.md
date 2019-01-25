# Open Spaces - Day 2

* Terraform
* Secrets Management in CI/CD Pipeline

## Terraform
* Use ConfigMgmt (Ansible,Puppet,Chef) for application/OS config; Terraform for infra provisioning; Packer can be used for images, etc.
* Terraform gives a clearer declarative language for infrastructure (Load Balancers, VMs, etc)
* Theoretically can trigger ```terraform apply``` from an Ansible playbook
* Structure of code repo for terraform?
    * Resource Module - Abstraction of resources; Usually shared freely 
    * Infrastructure Module - Abstraction of infrastructure; Usually org/place specific
    * Componsition
    * Suggested: All terraform code in one repo, linked to each microservice
    * Suggested: Split code into function driven repos, store remote state
    * Don't store state file in Git because merges will render it useless; Can store state file in a location like S3
    * Must be able access the storage location for terraform to use
    * Keep terraform files for different accounts seperate
    * AWS Systems Manager may help reconsile with ```terraform apply``` by more than 1 at a time
    * Take away access to the console to avoid drift from the terraform configuration; Must make sure that configs can happen in code
    * Someone built a Jenkins front end so ```git commit``` isn't been a reason to fear
    * Concern about persistance, like databases; Use terraform to create the database; Use other tools (ex. Ansible) to change password, handle creation of schema, etc
    * Suggested: Provide a script to developers to trigger ```terraform apply``` based on permissions they have directly.
    * Terraform will return errors if the API that the provider interacts with generates one based on conditions
    * Few people are replacing kops with terrform in EKS
    * Seperate projects for dyamic rapid changing v. more static elements; Note that AWS (and others?) will impose rate limiting to changes above a certain point
    * Inspect for infra testing

## Secrets Management in CI/CD Pipeline