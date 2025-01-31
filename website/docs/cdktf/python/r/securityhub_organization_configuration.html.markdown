---
subcategory: "Security Hub"
layout: "aws"
page_title: "AWS: aws_securityhub_organization_configuration"
description: |-
  Manages the Security Hub Organization Configuration
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_securityhub_organization_configuration

Manages the Security Hub Organization Configuration.

~> **NOTE:** This resource requires an [`aws_securityhub_organization_admin_account`](/docs/providers/aws/r/securityhub_organization_admin_account.html) to be configured (not necessarily with Terraform). More information about managing Security Hub in an organization can be found in the [Managing administrator and member accounts](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-accounts.html) documentation

~> **NOTE:** This is an advanced Terraform resource. Terraform will automatically assume management of the Security Hub Organization Configuration without import and perform no actions on removal from the Terraform configuration.

## Example Usage

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
#
# Provider bindings are generated by running `cdktf get`.
# See https://cdk.tf/provider-generation for more details.
#
from imports.aws.organizations_organization import OrganizationsOrganization
from imports.aws.securityhub_organization_admin_account import SecurityhubOrganizationAdminAccount
from imports.aws.securityhub_organization_configuration import SecurityhubOrganizationConfiguration
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
        example = OrganizationsOrganization(self, "example",
            aws_service_access_principals=["securityhub.amazonaws.com"],
            feature_set="ALL"
        )
        aws_securityhub_organization_admin_account_example =
        SecurityhubOrganizationAdminAccount(self, "example_1",
            admin_account_id="123456789012",
            depends_on=[example]
        )
        # This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.
        aws_securityhub_organization_admin_account_example.override_logical_id("example")
        aws_securityhub_organization_configuration_example =
        SecurityhubOrganizationConfiguration(self, "example_2",
            auto_enable=True
        )
        # This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.
        aws_securityhub_organization_configuration_example.override_logical_id("example")
```

## Argument Reference

This resource supports the following arguments:

* `auto_enable` - (Required) Whether to automatically enable Security Hub for new accounts in the organization.
* `auto_enable_standards` - (Optional) Whether to automatically enable Security Hub default standards for new member accounts in the organization. By default, this parameter is equal to `DEFAULT`, and new member accounts are automatically enabled with default Security Hub standards. To opt out of enabling default standards for new member accounts, set this parameter equal to `NONE`.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `id` - AWS Account ID.

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import an existing Security Hub enabled account using the AWS account ID. For example:

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
```

Using `terraform import`, import an existing Security Hub enabled account using the AWS account ID. For example:

```console
% terraform import aws_securityhub_organization_configuration.example 123456789012
```

<!-- cache-key: cdktf-0.20.0 input-5b0a80355870042433f0256e95b1b1ca23a8a89ac8d72a202dca64a9bd9f9132 -->