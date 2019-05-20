---
layout: default
title: ansible_group
parent: Resources
nav_order: 1
---
## Example Usage
```hcl
resource "ansible_group" "web" {
  inventory_group_name = "web"
  children             = ["foo", "bar", "baz"]
  vars = {
    foo = "bar"
    bar = 2
  }
}
```

## Argument Reference

The following arguments are suported:

- `inventory_group_name` - (Required) The group name that will be used by ansible in the dynamic inventory.
- `children` - (Optional) A list of Ansible groups that will be children of this group.
- `vars` - (Optional) A map of string values that will be attached to the Ansible group as group variables.

## Attributes Reference

The following attributes are exported:

- `id` - The TFState ID field of the resource. This will be the same as `inventory_group_name`.