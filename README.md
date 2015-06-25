# cookbook-nat

Cookbook to set up a non CentOS NAT instance for AWS VPCs.

This is an _opiniated_ cookbook and makes a bunch of assumptions about how
your NAT instance and VPC is set up so it may not work for your needs.

It is assumed that:

- There will be one NAT instance per AZ
- Your private subnets have a `network` tag with the value `private`
- Your route tables for private subnets have a `network` tag with the value `private`

This way NAT instances can be placed in an AutoScaling group. When they come up a simple
Chef run can update the relevant routes.

## Requirements

Only tested on Ubuntu 14.04, but should work on earlier versions. Depends on our [aws](https://github.com/kinesisptyltd/cookbook-aws)
cookbook.

## Recipes

### nat::default

Runs the `aws`, `network` and `hints` recipes.

## Attributes

### nat::default

Key                    | Type   | Description
:----------------------|--------|----------------------------------------------------------
`["nat"]["cidr"]`      | String | Source IP range to masquerade. Defaults to `10.10.0.0/16`

## Usage

Just include `nat` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[nat]"
  ]
}
```
