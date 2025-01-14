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
  expires_at                  = "2030-01-01T00:00:00Z"
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
The possible ACLs are:
  - `search`: allowed to perform search operations.
  - `browse`: allowed to retrieve all index data with the browse endpoint.
  - `addObject`: allowed to add or update a records in the index.
  - `deleteObject`: allowed to delete an existing record.
  - `listIndexes`: allowed to get a list of all existing indices.
  - `deleteIndex`: allowed to delete an index.
  - `settings`: allowed to read all index settings.
  - `editSettings`: allowed to update all index settings.
  - `analytics`: allowed to retrieve data with the Analytics API.
  - `recommendation`: allowed to interact with the Recommendation API.
  - `usage` allowed to retrieve data with the Usage API.
  - `nluReadAnswers`: allowed to perform semantic search with the Answers API.
  - `logs`: allowed to query the logs.
  - `seeUnretrievableAttributes`: allowed to retrieve unretrievableAttributes for all operations that return records.

### Optional

- **description** (String) Description of the API key.
- **expires_at** (String) Unix timestamp of the date at which the key expires. RFC3339 format. Will not expire per default.
- **id** (String) The ID of this resource.
- **indexes** (Set of String) List of targeted indices. You can target all indices starting with a prefix or ending with a suffix using the ‘*’ character. For example, “dev_*” matches all indices starting with “dev_” and “*_dev” matches all indices ending with “_dev”.
- **max_hits_per_query** (Number) Maximum number of hits this API key can retrieve in one call. This parameter can be used to protect you from attempts at retrieving your entire index contents by massively querying the index.
- **max_queries_per_ip_per_hour** (Number) Maximum number of API calls allowed from an IP address per hour.Each time an API call is performed with this key, a check is performed. If the IP at the source of the call did more than this number of calls in the last hour, a 429 code is returned.

This parameter can be used to protect you from attempts at retrieving your entire index contents by massively querying the index.
- **referers** (Set of String) List of referrers that can perform an operation. You can use the “*” (asterisk) character as a wildcard to match subdomains, or all pages of a website. For example, `"https://algolia.com/\*"` matches all referrers starting with `"https://algolia.com/"`, and `"\*.algolia.com"` matches all referrers ending with `".algolia.com"`. If you want to allow all possible referrers from the `algolia.com` domain, you can use `"\*algolia.com/\*"`.

### Read-Only

- **created_at** (Number) The unix time at which the key has been created.
- **key** (String, Sensitive) The created key.

## Import

Import is supported using the following syntax:

```shell
terraform import algolia_api_key.default {{key}}
```
