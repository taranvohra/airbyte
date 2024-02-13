# Lemlist

## Sync overview

The Lemlist source supports Full Refresh syncs only.

This source can sync data for the [Lemlist API](https://developer.lemlist.com/#introduction).

### Output schema

This Source is capable of syncing the following core Streams:

* [Team](https://github.com/taranvohra/airbyte/blob/master/docs/integrations/sources/%60api.lemlist.com/api/team%60/README.md)
* [Campaigns](https://github.com/taranvohra/airbyte/blob/master/docs/integrations/sources/%60api.lemlist.com/api/campaigns%60/README.md)
* [Activities](https://github.com/taranvohra/airbyte/blob/master/docs/integrations/sources/%60api.lemlist.com/api/activities%60/README.md)
* [Unsubscribes](https://github.com/taranvohra/airbyte/blob/master/docs/integrations/sources/%60api.lemlist.com/api/unsubscribes%60/README.md)

### Features

| Feature                   | Supported?(Yes/No) | Notes |
| ------------------------- | ------------------ | ----- |
| Full Refresh Sync         | Yes                |       |
| Incremental - Append Sync | No                 |       |
| Namespaces                | No                 |       |

### Performance considerations

The Lemlist connector should not run into Lemlist API limitations under normal usage. Please [create an issue](https://github.com/airbytehq/airbyte/issues) if you see any rate limit issues that are not automatically retried successfully.

## Getting started

### Requirements

* Lemlist API key

## Changelog

| Version | Date       | Pull Request                                           | Subject         |
| ------- | ---------- | ------------------------------------------------------ | --------------- |
| 0.1.0   | 2021-10-14 | [7062](https://github.com/airbytehq/airbyte/pull/7062) | Initial Release |
