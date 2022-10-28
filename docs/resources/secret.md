---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tss_secret Resource - terraform-provider-tss"
subcategory: ""
description: |-
  
---

# tss_secret (Resource)

This resource creates a secret in Secret Server

## Example Usage

```hcl

resource "tss_secret" "mysecret" {
  name = "mysecret"
  secret_template_id = 2
  folder_id = 1
  all_fields = false
  fields {
    field_name = "Password"
    field_value = "secretpassword"
  }
}

```

## Argument Reference

* `name` - Required
* `secret_template_id` - Required
* `folder_id` - Required
* `all_fields` - (Optional) Defaults to false. If set to true the provider will fetch all fields when refreshing state, otherwise the default behaviour is to only care about the fields provided in the fields-block.
* `fields` - (Required) Every tss_secret resource must have at least 1 fields-block

Fields-block:
* `field_id` - (Optional) The provider will find this value from `field_name`, if the user has "View Secret Templates"-permission in Secret Server
* `field_name`- (Required) The name of the field
* `field_value`- (Required) The value of the field