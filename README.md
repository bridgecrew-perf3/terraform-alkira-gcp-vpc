# Alkira GCP Connector - Terraform Module
This module makes it easy to provision an [GCP VPC](https://cloud.google.com/vpc) and connect it through [Alkira](htts://alkira.com).

## What it does
- Build a [VPC](https://cloud.google.com/vpc) and one or more [subnets](https://cloud.google.com/vpc/docs/vpc#subnet-ranges)
- Create an [Alkira Connector](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/resources/connector_gcp_vpc) for the new VPC
- Apply an existing [Billing Tag](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/billing_tag) to the connector
- Place resources in an existing [segment](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/segment) and [group](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/group)


<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13.1 |
| <a name="requirement_alkira"></a> [alkira](#requirement\_alkira) | >= 0.8.0 |
| <a name="requirement_google"></a> [google](#requirement\_google) | <5.0,>= 2.12 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alkira"></a> [alkira](#provider\_alkira) | >= 0.8.0 |
| <a name="provider_google"></a> [google](#provider\_google) | <5.0,>= 2.12 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [alkira_connector_gcp_vpc.connector](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/resources/connector_gcp_vpc) | resource |
| [google_compute_network.vpc](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_network) | resource |
| [google_compute_subnetwork.gcp_subnet](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_subnetwork) | resource |
| [alkira_billing_tag.tag](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/billing_tag) | data source |
| [alkira_credential.credential](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/credential) | data source |
| [alkira_group.group](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/group) | data source |
| [alkira_segment.segment](https://registry.terraform.io/providers/alkiranet/alkira/latest/docs/data-sources/segment) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_billing_tag"></a> [billing\_tag](#input\_billing\_tag) | Alkira - billing tag | `string` | n/a | yes |
| <a name="input_credential"></a> [credential](#input\_credential) | Alkira - cloud credential | `string` | n/a | yes |
| <a name="input_cxp"></a> [cxp](#input\_cxp) | Alkira - CXP to add connector to | `string` | n/a | yes |
| <a name="input_gcp_region"></a> [gcp\_region](#input\_gcp\_region) | GCP region for routing Alkira | `string` | n/a | yes |
| <a name="input_group"></a> [group](#input\_group) | Alkira - group to add connector to | `string` | n/a | yes |
| <a name="input_name"></a> [name](#input\_name) | Name of cloud network and Alkira connector | `string` | n/a | yes |
| <a name="input_project_id"></a> [project\_id](#input\_project\_id) | GCP project ID that owns or contains calling entity | `string` | n/a | yes |
| <a name="input_routing_mode"></a> [routing\_mode](#input\_routing\_mode) | VPC routing mode | `string` | `"GLOBAL"` | no |
| <a name="input_segment"></a> [segment](#input\_segment) | Alkira - segment to add connector to | `string` | n/a | yes |
| <a name="input_size"></a> [size](#input\_size) | Alkira - connector size | `string` | `"SMALL"` | no |
| <a name="input_subnets"></a> [subnets](#input\_subnets) | Subnets to create for cloud network | `list(map(string))` | <pre>[<br>  {}<br>]</pre> | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_connector_cxp"></a> [connector\_cxp](#output\_connector\_cxp) | CXP that connector was provisioned in |
| <a name="output_connector_group"></a> [connector\_group](#output\_connector\_group) | Group that connector was added to |
| <a name="output_connector_id"></a> [connector\_id](#output\_connector\_id) | ID of the connector |
| <a name="output_connector_name"></a> [connector\_name](#output\_connector\_name) | Name of the connector |
| <a name="output_connector_segment_id"></a> [connector\_segment\_id](#output\_connector\_segment\_id) | Segment that connector was placed in |
| <a name="output_connector_size"></a> [connector\_size](#output\_connector\_size) | Size of the connector |
| <a name="output_subnet"></a> [subnet](#output\_subnet) | GCP subnet configuration |
| <a name="output_vpc_id"></a> [vpc\_id](#output\_vpc\_id) | GCP VPC ID |
| <a name="output_vpc_name"></a> [vpc\_name](#output\_vpc\_name) | GCP VPC name |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
