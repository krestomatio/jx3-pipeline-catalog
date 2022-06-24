## Multiarch builder tasks

These tasks contain reusable steps for deploying or undeploying multiarch-builder instances in a release or pull request pipeline.

## Require variables
The following are required variables. They could be place in secret called `multiarch-builder-envvars`.

```
AWS_ACCESS_KEY_ID=<aws_access_key_id>
AWS_SECRET_ACCESS_KEY=<aws_secret_access_key>
AWS_DEFAULT_REGION=<aws_default_region>
TF_VAR_subnet_id=<aws_subnet_id>
TF_VAR_security_group_ids=["<aws_sg_id>"]
TF_VAR_create_client_certs=true
TF_VAR_handle_client_config=true
# `TF_VAR_prefix_name` is a set based on other variables from Jenkins X (JX). If not using JX, you may want to set it.
```
To check all `TF_` variables available, check [the module repo](github.com/krestomatio/terraform-aws-multiarch-builder)
