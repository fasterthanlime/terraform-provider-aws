---
subcategory: "Connect"
layout: "aws"
page_title: "AWS: aws_connect_security_profile"
description: |-
  Provides details about a specific Amazon Connect Security Profile.
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_connect_security_profile

Provides an Amazon Connect Security Profile resource. For more information see
[Amazon Connect: Getting Started](https://docs.aws.amazon.com/connect/latest/adminguide/amazon-connect-get-started.html)

## Example Usage

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
#
# Provider bindings are generated by running `cdktf get`.
# See https://cdk.tf/provider-generation for more details.
#
from imports.aws.connect_security_profile import ConnectSecurityProfile
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
        ConnectSecurityProfile(self, "example",
            description="example description",
            instance_id="aaaaaaaa-bbbb-cccc-dddd-111111111111",
            name="example",
            permissions=["BasicAgentAccess", "OutboundCallAccess"],
            tags={
                "Name": "Example Security Profile"
            }
        )
```

## Argument Reference

This resource supports the following arguments:

* `description` - (Optional) Specifies the description of the Security Profile.
* `instance_id` - (Required) Specifies the identifier of the hosting Amazon Connect Instance.
* `name` - (Required) Specifies the name of the Security Profile.
* `permissions` - (Optional) Specifies a list of permissions assigned to the security profile.
* `tags` - (Optional) Tags to apply to the Security Profile. If configured with a provider
[`default_tags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block) present, tags with matching keys will overwrite those defined at the provider-level.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `arn` - The Amazon Resource Name (ARN) of the Security Profile.
* `organization_resource_id` - The organization resource identifier for the security profile.
* `security_profile_id` - The identifier for the Security Profile.
* `id` - The identifier of the hosting Amazon Connect Instance and identifier of the Security Profile separated by a colon (`:`).
* `tags_all` - A map of tags assigned to the resource, including those inherited from the provider [`default_tags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block).

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import Amazon Connect Security Profiles using the `instance_id` and `security_profile_id` separated by a colon (`:`). For example:

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
```

Using `terraform import`, import Amazon Connect Security Profiles using the `instance_id` and `security_profile_id` separated by a colon (`:`). For example:

```console
% terraform import aws_connect_security_profile.example f1288a1f-6193-445a-b47e-af739b2:c1d4e5f6-1b3c-1b3c-1b3c-c1d4e5f6c1d4e5
```

<!-- cache-key: cdktf-0.20.0 input-220f16e830e0261ed2fda1556d594951dc89e406092f917b2ad3ea75fafbac54 -->