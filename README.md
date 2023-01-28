<!-- BEGIN_TF_DOCS -->
## Overview
An output-only module for converting between units of time, with the intent of producing more readable and less error-prone duration configurations.


### Usage

Without this module:
```terraform
resource "dns_a_record_set" "www" {
  zone = "example.com."
  name = "www"
  addresses = [
    "192.168.0.1"
  ]
  ttl = 43200
}
```

With this module:
```terraform
module "durations" {
  source = "github.com/shils/terraform-duration-conversions"
}

resource "dns_a_record_set" "www" {
  zone = "example.com."
  name = "www"
  addresses = [
    "192.168.0.1"
  ]
  ttl = 12 * module.durations.hours_to_seconds
}
```

### Future 
This module won't be necessary once one of the following proposals are implemented:
* https://github.com/hashicorp/terraform/issues/27063
* https://github.com/hashicorp/terraform/pull/27048
* https://github.com/hashicorp/terraform/issues/2771

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_days_to_hours"></a> [days\_to\_hours](#output\_days\_to\_hours) | The number of hours in a day |
| <a name="output_days_to_millis"></a> [days\_to\_millis](#output\_days\_to\_millis) | The number of milliseconds in a day |
| <a name="output_days_to_minutes"></a> [days\_to\_minutes](#output\_days\_to\_minutes) | The number of minutes in a day |
| <a name="output_days_to_seconds"></a> [days\_to\_seconds](#output\_days\_to\_seconds) | The number of seconds in a day |
| <a name="output_hours_to_millis"></a> [hours\_to\_millis](#output\_hours\_to\_millis) | The number of milliseconds in an hour |
| <a name="output_hours_to_minutes"></a> [hours\_to\_minutes](#output\_hours\_to\_minutes) | The number of minutes in an hour |
| <a name="output_hours_to_seconds"></a> [hours\_to\_seconds](#output\_hours\_to\_seconds) | The number of seconds in an hour |
| <a name="output_minutes_to_millis"></a> [minutes\_to\_millis](#output\_minutes\_to\_millis) | The number of milliseconds in a minute |
| <a name="output_minutes_to_seconds"></a> [minutes\_to\_seconds](#output\_minutes\_to\_seconds) | The number of seconds in a minute |
| <a name="output_seconds_to_millis"></a> [seconds\_to\_millis](#output\_seconds\_to\_millis) | The number of milliseconds in a second |
| <a name="output_weeks_to_days"></a> [weeks\_to\_days](#output\_weeks\_to\_days) | The number of days in a week |
| <a name="output_weeks_to_hours"></a> [weeks\_to\_hours](#output\_weeks\_to\_hours) | The number of hours in a week |
| <a name="output_weeks_to_millis"></a> [weeks\_to\_millis](#output\_weeks\_to\_millis) | The number of milliseconds in a week |
| <a name="output_weeks_to_minutes"></a> [weeks\_to\_minutes](#output\_weeks\_to\_minutes) | The number of minutes in a week |
| <a name="output_weeks_to_seconds"></a> [weeks\_to\_seconds](#output\_weeks\_to\_seconds) | The number of seconds in a week |
<!-- END_TF_DOCS -->