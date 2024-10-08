# Data Source `runscope_bucket`

Use this data source to get information about a specific [bucket](https://www.runscope.com/docs/api/buckets)
that you can use with other runscope resources.

## Example Usage

```hcl
data "runscope_bucket" "website" {
  key = "t2f4bkvnggct"
}

resource "runscope_environment" "environment" {
  bucket_id = runscope_bucket.website.id
  name      = "test-environment"
}
```

## Argument Reference

The following arguments are supported:

* `key` - (Required) The unique key of the bucket.

## Attributes Reference

The following attributes are exported:

* `id` - The unique key of the found bucket.
* `team_uuid` - The team unique identifier that owns the bucket.
* `name` - Type name of the bucket.
* `auth_token` - Bucket auth token if set.
* `default` - `true` if this bucket is the 'default' for a team.
* `verify_ssl` - `true` if this bucket is configured to verify ssl for requests made to it.
* `trigger_url` - URL to trigger a test run for all tests within a bucket.
