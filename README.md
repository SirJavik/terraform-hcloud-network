# Terraform Module: Network

This Terraform module creates a network infrastructure in the cloud provider of your choice. It provisions the necessary resources such as virtual networks, subnets, security groups, and routing tables.

## Features

- Creates a virtual network with customizable CIDR block.
- Configures subnets with different availability zones.
- Sets up security groups to control inbound and outbound traffic.
- Configures routing tables for efficient network traffic.

## Usage

```hcl
module "network" {
    source = "git::https://github.com/your-organization/terraform-network-module.git"

    name            = "my-network"
    cidr_block      = "10.0.0.0/16"
    availability_zones = ["us-west-2a", "us-west-2b", "us-west-2c"]
}
```

## Inputs

| Name                  | Description                             | Type   | Default | Required |
|-----------------------|-----------------------------------------|--------|---------|----------|
| name                  | Name of the network                      | string | n/a     | yes      |
| cidr_block            | CIDR block for the network               | string | n/a     | yes      |
| availability_zones    | List of availability zones               | list   | n/a     | yes      |

## Outputs

| Name                  | Description                             |
|-----------------------|-----------------------------------------|
| vpc_id                | ID of the created virtual private cloud  |
| subnet_ids            | IDs of the created subnets               |
| security_group_ids    | IDs of the created security groups       |
| route_table_ids       | IDs of the created route tables          |

## License

This module is licensed under the [MIT License](https://opensource.org/licenses/MIT).
