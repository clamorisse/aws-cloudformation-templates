# aws-cloudformation-templates

This repository contains AWS Cloudformation templates to provision infrustructure for different types of applications from ground up.

## How to use it

```bash
# create a stack using template name checked out from gti
aws cloudformation create-stack --stack-name myblogCF  --template-body file://website-vpc-infra.template

# get a beer and watch how Amazon creates stuff for you in automatic mode
watch -n 1 "aws cloudformation describe-stack-events --stack-name myblogCF  | jq -r '.StackEvents[] | [.ResourceStatus, .ResourceStatusReason, .ResourceType] | @tsv'"

# if something fails, delete stack, edit template and create it again
aws cloudformation delete-stack --stack-name myblogCF

# change something in template and run update-stack to see changes applied
aws cloudformation update-stack --stack-name myblogCF  --template-body file://website-vpc-infra.template


```
