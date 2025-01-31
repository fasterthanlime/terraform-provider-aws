---
subcategory: "IoT Core"
layout: "aws"
page_title: "AWS: aws_iot_thing_group"
description: |-
    Manages an AWS IoT Thing Group.
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_iot_thing_group

Manages an AWS IoT Thing Group.

## Example Usage

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
#
# Provider bindings are generated by running `cdktf get`.
# See https://cdk.tf/provider-generation for more details.
#
from imports.aws.iot_thing_group import IotThingGroup
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
        parent = IotThingGroup(self, "parent",
            name="parent"
        )
        IotThingGroup(self, "example",
            name="example",
            parent_group_name=parent.name,
            properties=IotThingGroupProperties(
                attribute_payload=IotThingGroupPropertiesAttributePayload(
                    attributes={
                        "One": "11111",
                        "Two": "TwoTwo"
                    }
                ),
                description="This is my thing group"
            ),
            tags={
                "terraform": "true"
            }
        )
```

## Argument Reference

* `name` - (Required) The name of the Thing Group.
* `parent_group_name` - (Optional) The name of the parent Thing Group.
* `properties` - (Optional) The Thing Group properties. Defined below.
* `tags` - (Optional) Key-value mapping of resource tags

### properties Reference

* `attribute_payload` - (Optional) The Thing Group attributes. Defined below.
* `description` - (Optional) A description of the Thing Group.

### attribute_payload Reference

* `attributes` - (Optional) Key-value map.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `arn` - The ARN of the Thing Group.
* `id` - The Thing Group ID.
* `version` - The current version of the Thing Group record in the registry.

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import IoT Things Groups using the name. For example:

```python
# DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
from constructs import Construct
from cdktf import TerraformStack
class MyConvertedCode(TerraformStack):
    def __init__(self, scope, name):
        super().__init__(scope, name)
```

Using `terraform import`, import IoT Things Groups using the name. For example:

```console
% terraform import aws_iot_thing_group.example example
```

<!-- cache-key: cdktf-0.20.0 input-d40a8b9d3295130dee82fc924f5a78064a2bcbc1d9fdc3faf7a58c297c82b090 -->