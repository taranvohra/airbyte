# Looker

## Overview

The Looker source supports Full Refresh syncs. That is, every time a sync is run, Airbyte will copy all rows in the tables and columns you set up for replication into the destination in a new table.

### Output schema

Several output streams are available from this source:

* [Color Collections](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/color-collection#get\_all\_color\_collections)
* [Connections](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/connection#get\_all\_connections)
* [Content Metadata](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/content#get\_all\_content\_metadatas)
* [Content Metadata Access](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/content#get\_all\_content\_metadata\_accesses)
* [Dashboards](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/dashboard#get\_all\_dashboards)
  * [Dashboard Elements](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/dashboard#get\_all\_dashboardelements)
  * [Dashboard Filters](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/dashboard#get\_all\_dashboard\_filters)
  * [Dashboard Layouts](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/dashboard#get\_all\_dashboardlayouts)
* [Datagroups](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/datagroup#get\_all\_datagroups)
* [Folders](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/folder#get\_all\_folders)
* [Groups](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/group#get\_all\_groups)
* [Homepages](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/homepage#get\_all\_homepages)
* [Integration Hubs](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/integration#get\_all\_integration\_hubs)
* [Integrations](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/integration#get\_all\_integrations)
* [Lookml Dashboards](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/dashboard#get\_all\_dashboards)
* [Lookml Models](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/lookml-model#get\_all\_lookml\_models)
* [Looks](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/look#get\_all\_looks)
  * [Run Look](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/look#run\_look)
* [Projects](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/project#get\_all\_projects)
  * [Project Files](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/project#get\_all\_project\_files)
  * [Git Branches](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/project#get\_all\_git\_branches)
* [Query History](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/query#run\_query)
* [Roles](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/role#get\_all\_roles)
  * [Model Sets](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/role#get\_all\_model\_sets)
  * [Permission Sets](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/role#get\_all\_permission\_sets)
  * [Permissions](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/role#get\_all\_permissions)
  * [Role Groups](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/role#get\_role\_groups)
* [Scheduled Plans](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/scheduled-plan#get\_all\_scheduled\_plans)
* [Spaces](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/space#get\_all\_spaces)
* [User Attributes](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/user-attribute#get\_all\_user\_attributes)
  * [User Attribute Group Value](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/user-attribute#get\_user\_attribute\_group\_values)
* [User Login Lockouts](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/auth#get\_all\_user\_login\_lockouts)
* [Users](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/user#get\_all\_users)
  * [User Attribute Values](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/user#get\_user\_attribute\_values)
  * [User Sessions](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/user#get\_all\_web\_login\_sessions)
* [Versions](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/config#get\_apiversion)
* [Workspaces](https://docs.looker.com/reference/api-and-integration/api-reference/v3.1/workspace)

If there are more endpoints you'd like Airbyte to support, please [create an issue.](https://github.com/airbytehq/airbyte/issues/new/choose)

### Features

| Feature                       | Supported?  |
| ----------------------------- | ----------- |
| Full Refresh Sync             | Yes         |
| Incremental Sync              | Coming soon |
| Replicate Incremental Deletes | Coming soon |
| SSL connection                | Yes         |
| Namespaces                    | No          |

### Performance considerations

The Looker connector should not run into Looker API limitations under normal usage. Please [create an issue](https://github.com/airbytehq/airbyte/issues) if you see any rate limit issues that are not automatically retried successfully.

## Getting started

### Requirements

* Client Id
* Client Secret
* Domain

### Setup guide

Please read the "API3 Key" section in [Looker's information for users docs](https://docs.looker.com/admin-options/settings/users) for instructions on how to generate Client Id and Client Secret.

## CHANGELOG

| Version | Date       | Pull Request                                            | Subject                                                  |
| ------- | ---------- | ------------------------------------------------------- | -------------------------------------------------------- |
| 0.2.7   | 2022-01-24 | [#9609](https://github.com/airbytehq/airbyte/pull/9609) | Migrate to native CDK and fixing of intergration tests   |
| 0.2.6   | 2021-12-07 | [#8578](https://github.com/airbytehq/airbyte/pull/8578) | Updated titles and descriptions                          |
| 0.2.5   | 2021-10-27 | [#7284](https://github.com/airbytehq/airbyte/pull/7284) | Migrate Looker source to CDK structure, add SAT testing. |
| 0.2.4   | 2021-06-25 | [#3911](https://github.com/airbytehq/airbyte/pull/3911) | Added `run_look` endpoint.                               |
| 0.2.3   | 2021-06-22 | [#3587](https://github.com/airbytehq/airbyte/pull/3587) | Added support for self-hosted instances.                 |
| 0.2.2   | 2021-06-09 | [#3973](https://github.com/airbytehq/airbyte/pull/3973) | Added `AIRBYTE_ENTRYPOINT` for kubernetes support.       |
| 0.2.1   | 2021-04-02 | [#2726](https://github.com/airbytehq/airbyte/pull/2726) | Fixed connector base versioning.                         |
| 0.2.0   | 2021-03-09 | [#2238](https://github.com/airbytehq/airbyte/pull/2238) | Allowed future / unknown properties in the protocol.     |
| 0.1.1   | 2021-01-27 | [#1857](https://github.com/airbytehq/airbyte/pull/1857) | Fix failed CI tests.                                     |
| 0.1.0   | 2020-12-24 | [#1441](https://github.com/airbytehq/airbyte/pull/1441) | Added looker connector.                                  |
