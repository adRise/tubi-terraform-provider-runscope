## 0.11.0 (Unreleased)

* Validate enumerated attributes
  * runscope_schedule.interval
  * runscope_step.variable.source
  * runscope_step.assertion.source
  * runscope_step.assertion.comparison
  
## 0.10.0 (April 24, 2021)

ENHANCEMENTS:

* Added attributes `auth_token`, `default` and `verify_ssl` of `runscope_bucket`.
* Added attributes `stop_on_failure`, `parent_environment_id` and `client_certificate` of `runscope_environment`.
* Only changing of `bucket_id` and `test_id` forces new `runscope_environment`.
* Added attributes `skipped` and `form_parameter` of `runscope_step`.
* Require arguments `method` and `url` of `runscope_step`, and don't force new step when they are changed.
* Added attributes `created_at`, `created_by` and `trigger_url` of `runscope_test`.
* Changing of test arguments no more forces new test.
* Added attribute `exported_at` of `runscope_schedule`.
* Require argument `interval` of `runscope_schedule` is required and no more forces new schedule.
* Changing of `interval` and `note` no more forces new schedule.

BUG FIXES:

* Fixed issue with step updating (appeared in 0.9.1).

## 0.9.1 (April 10, 2021)

NOTES:

* Resources are reimplemented using internal context-aware client library.
  go-runscope removed from dependencies.

## 0.9.0 (April 1, 2021)

BREAKING CHANGES:

* Removed deprecated attributes `remote_agents` and `emails` of `runscope_environment`
  and `variables`, `assertions` and `headers` of `runscope_step`.
* If `runscope_environment.email` omitted, email notification settings are resetting to defaults.
* Recipient ID is required to configure `runscope_environment.email.recipient`.
  `name` and `email` of `recipient` are computed.
* Terraform Plugin SDK is updated to 2.4.3, so you need terraform >= 0.12 to use provider.

## 0.8.0 (March 29, 2021)

NOTES:

* Deprecated attributes `remote_agents` and `emails` of `runscope_environment`.
  Use `remote_agent` and `email` instead.
* Deprecated attribute `variables`, `assertions` and `headers` of `runscope_step`.
  Use `variable`, `assertion`, `header` instead.

ENHANCEMENTS:

* Added attributes `remote_agent` and `email` of `runscope_environment`.
* Added attribute `variable`, `assertion` and `header` of `runscope_step`.

## 0.7.0 (March 27, 2021)

ENHANCEMENTS:

* Added import of `runscope_test` resource.
* Added import of `runscope_step` resource.

BUG FIXES:

* Fixed issue with fractional schedule interval.

## 0.6.0 (June 30, 2019)

NOTES:

* This release includes a Terraform SDK upgrade with compatibility for Terraform v0.12. The provider remains backwards compatible with Terraform v0.11 and there should not be any significant behavioural changes. ([#27](https://github.com/terraform-providers/terraform-provider-runscope/issues/27))

## 0.5.0 (October 04, 2018)
ENHANCEMENTS:

*  resource/runscope_step: New attributes `note` added ([#16](https://github.com/terraform-providers/terraform-provider-runscope/pull/16))

## 0.4.0 (September 22, 2018)
ENHANCEMENTS:

*  resource/runscope_environment: New attributes `webhooks` and `emails` added ([#13](https://github.com/terraform-providers/terraform-provider-runscope/pull/13))
## 0.3.0 (July 26, 2018)

FEATURES:

* **New Data Source:** `runscope_bucket` ([#12](https://github.com/terraform-providers/terraform-provider-runscope/issues/12))
* **New Data Source:** `runscope_buckets` ([#12](https://github.com/terraform-providers/terraform-provider-runscope/issues/12))

ENHANCEMENTS:

*  resource/runscope_bucket: Import support added ([#12](https://github.com/terraform-providers/terraform-provider-runscope/issues/12))

## 0.2.0 (July 03, 2018)

ENHANCEMENTS:

* resource/runscope_test: No longer forces a new resource when the `name` attribute changes.

## 0.1.0 (June 21, 2018)

Initial release.

