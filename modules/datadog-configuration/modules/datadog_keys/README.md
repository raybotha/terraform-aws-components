# Submodule `datadog_keys`

Useful submodule for other modules to quickly configure the datadog provider

## Usage

```hcl
module "datadog_configuration" {
  source  = "../datadog-configuration/modules/datadog_keys"
  region = var.region
  context = module.this.context
}

provider "datadog" {
  api_url  = module.datadog_configuration.datadog_api_url
  api_key  = module.datadog_configuration.datadog_api_key
  app_key  = module.datadog_configuration.datadog_app_key
  validate = local.enabled
}
```

