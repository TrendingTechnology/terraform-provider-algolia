---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "algolia_api_key Resource - terraform-provider-algolia"
subcategory: ""
description: |-
  A configuration for an API key
---

# algolia_api_key (Resource)

A configuration for an API key

## Example Usage

```terraform
resource "algolia_api_key" "example" {
  acl                         = ["search", "browse"]
  expires_at                  = 2524608000 # 01 Jan 2050 00:00:00 GMT
  max_hits_per_query          = 100
  max_queries_per_ip_per_hour = 10000
  description                 = "This is a example api key"
  indexes                     = ["*"]
  referers                    = ["https://algolia.com/\\*"]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **acl** (Set of String) Set of permissions associated with the key.

### Optional

- **description** (String) Description of the API key.
- **expires_at** (Number) Unix timestamp of the date at which the key expires. A value of 0 means the API key doesn’t expire.
- **id** (String) The ID of this resource.
- **indexes** (Set of String) List of targeted indices. You can target all indices starting with a prefix or ending with a suffix using the ‘*’ character.
- **max_hits_per_query** (Number) Maximum number of hits this API key can retrieve in one call.
- **max_queries_per_ip_per_hour** (Number) Maximum number of API calls allowed from an IP address per hour.
- **referers** (Set of String) List of referrers that can perform an operation. You can use the “*” (asterisk) character as a wildcard to match subdomains, or all pages of a website.

### Read-Only

- **created_at** (Number) The unix time at which the key has been created.
- **key** (String, Sensitive) The created key.

