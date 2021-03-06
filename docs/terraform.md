## Providers

| Name | Version |
|------|---------|
| aws | ~> 2.0 >= 2.7.0 |
| local | n/a |
| template | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| api\_name | (Required) - The name of the REST API | `string` | n/a | yes |
| availability\_zones | (Required) - The AWS avaialbility zones (e.g. ap-southeast-2a/b/c). Autoloaded from region.tfvars. | `list(string)` | n/a | yes |
| function\_names | (Required) - Name of the Lambda function whose resource policy you are updating | `list(string)` | n/a | yes |
| api\_key\_source | (Optional) - The source of the API key for requests. Valid values are HEADER (default) and AUTHORIZER. | `string` | `"HEADER"` | no |
| attributes | (Optional) - Additional attributes (e.g. `1`) | `list(string)` | `[]` | no |
| aws\_account\_id | The AWS account id of the provider being deployed to (e.g. 12345678). Autoloaded from account.tfvars | `string` | `""` | no |
| aws\_assume\_role\_arn | (Optional) - ARN of the IAM role when optionally connecting to AWS via assumed role. Autoloaded from account.tfvars. | `string` | `""` | no |
| aws\_assume\_role\_external\_id | (Optional) - The external ID to use when making the AssumeRole call. | `string` | `""` | no |
| aws\_assume\_role\_session\_name | (Optional) - The session name to use when making the AssumeRole call. | `string` | `""` | no |
| aws\_region | The AWS region (e.g. ap-southeast-2). Autoloaded from region.tfvars. | `string` | `""` | no |
| binary\_media\_types | (Optional) - The list of binary media types supported by the RestApi. By default, the RestApi supports only UTF-8-encoded text payloads. | `list(string)` | `[]` | no |
| body | (Optional) - An OpenAPI specification that defines the set of routes and integrations to create as part of the REST API. | `string` | `""` | no |
| cognito\_userpool\_arn | Cognito userpool ARN for user authentication | `string` | `""` | no |
| delimiter | (Optional) - Delimiter to be used between `namespace`, `environment`, `stage`, `name` and `attributes` | `string` | `"-"` | no |
| description | (Optional) - The description of the role. | `string` | `"Managed by Terraform"` | no |
| enabled | (Optional) - A Switch that decides whether to create a terraform resource or run a provisioner. Default is true | `bool` | `true` | no |
| endpoint\_type | (Optional) -  (Required) A list of endpoint types. This resource currently only supports managing a single value. Valid values: EDGE, REGIONAL or PRIVATE. If unspecified, defaults to EDGE. | `string` | `"REGIONAL"` | no |
| environment | (Optional) - Environment, e.g. 'dev', 'qa', 'staging', 'prod' | `string` | `""` | no |
| minimum\_compression\_size | (Optional) Minimum response size to compress for the REST API. Integer between -1 and 10485760 (10MB). Setting a value greater than -1 will enable compression, -1 disables compression (default). | `string` | `"-1"` | no |
| name | (Optional) - Solution name, e.g. 'vault', 'consul', 'keycloak', 'k8s', or 'baseline' | `string` | `""` | no |
| namespace | (Optional) - Namespace, which could be your abbreviated product team, e.g. 'rci', 'mi', 'hp', or 'core' | `string` | `""` | no |
| policy | (Optional) - JSON formatted policy document that controls access to the API Gateway. | `string` | `""` | no |
| quota\_settings | (Optional) - Quota Settings Arguments. Full details can be found here https://www.terraform.io/docs/providers/aws/r/api\_gateway\_usage\_plan.html | <code><pre>object({<br>    limit  = number<br>    offset = number<br>    period = string<br>  })<br></pre></code> | <code><pre>{<br>  "limit": 1000000,<br>  "offset": 1,<br>  "period": "MONTH"<br>}<br></pre></code> | no |
| tags | (Optional) - Additional tags | `map(string)` | `{}` | no |
| throttle\_settings | (Optional) - Throttle Settings Arguments. Full details can be found here https://www.terraform.io/docs/providers/aws/r/api\_gateway\_usage\_plan.html | <code><pre>object({<br>    burst_limit = number<br>    rate_limit  = number<br>  })<br></pre></code> | <code><pre>{<br>  "burst_limit": 10,<br>  "rate_limit": 20<br>}<br></pre></code> | no |
| vpc\_endpoint\_ids | (Optional) - A list of VPC Endpoint Ids. It is only supported for PRIVATE endpoint type. | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| api\_id | The ID of the REST API |
| arn | The Amazon Resource Name (ARN) |
| created\_date | The creation date of the REST API |
| execution\_arn | The execution ARN part to be used in lambda\_permission's source\_arn when allowing API Gateway to invoke a Lambda function, e.g. arn:aws:execute-api:eu-west-2:123456789012:z4675bid1j, which can be concatenated with allowed stage, method and resource path. |

