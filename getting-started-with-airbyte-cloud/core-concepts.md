# Core Concepts

Airbyte enables you to build data pipelines and replicate data from a source to a destination. You can configure how frequently the data is synced, what data is replicated, what format the data is written to in the destination, and if the data is stored in raw tables format or basic normalized (or JSON) format.

This page describes the concepts you need to know to use Airbyte.

## Source

A source is an API, file, database, or data warehouse that you want to ingest data from.

## Destination

A destination is a data warehouse, data lake, database, or an analytics tool where you want to load your ingested data.

## Connector

An Airbyte component which pulls data from, or pushes data to, a source or destination.

## Connection

A connection is an automated data pipeline that replicates data from a source to a destination.

Setting up a connection involves configuring the following parameters:

| **Parameter**                          | **Description**                                                                                         |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Sync schedule                          | When should a data sync be triggered?                                                                   |
| Destination Namespace and stream names | Where should the replicated data be written?                                                            |
| Catalog selection                      | What data should be replicated from the source to the destination?                                      |
| Sync mode                              | How should the streams be replicated (read and written)?                                                |
| Optional transformations               | How should Airbyte protocol messages (raw JSON blob) data be converted into other data representations? |

## Stream

A stream is a group of related records.

Examples of streams:

* A table in a relational database
* A resource or API endpoint for a REST API
* The records from a directory containing many files in a filesystem

## Field

A field is an attribute of a record in a stream.

Examples of fields:

* A column in the table in a relational database
* A field in an API response

## Namespace

Namespace is a group of streams in a source or destination. Common use cases for namespaces are enforcing permissions, segregating test and production data, and general data organization.

A schema in a relational database system is an example of a namespace.

In a source, the namespace is the location from where the data is replicated to the destination.

In a destination, the namespace is the location where the replicated data is stored in the destination. Airbyte supports the following configuration options for destination namespaces:

| **Configuration**       | **Description**                                                                                                                                                                                                                                                                                                                                    |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mirror source structure | Some sources (for example, databases) provide namespace information for a stream. If a source provides the namespace information, the destination will reproduce the same namespace when this configuration is set. For sources or streams where the source namespace is not known, the behavior will default to the "Destination default" option. |
| Destination default     | All streams will be replicated and stored in the default namespace defined on the destination settings page. For settings for popular destinations, see[ ​​Destination Connector Settings](https://docs.airbyte.com/understanding-airbyte/namespaces#destination-connector-settings)                                                               |
| Custom format           | All streams will be replicated and stored in a user-defined custom format. See[ Custom format](https://docs.airbyte.com/understanding-airbyte/namespaces#custom-format) for more details.                                                                                                                                                          |

## Connection sync modes

A sync mode governs how Airbyte reads from a source and writes to a destination. Airbyte provides different sync modes to account for various use cases.

* **Full Refresh | Overwrite:** Sync all records from the source and replace data in destination by overwriting it.
* **Full Refresh | Append:** Sync all records from the source and add them to the destination without deleting any data.
* **Incremental Sync | Append:** Sync new records from the source and add them to the destination without deleting any data.
* **Incremental Sync | Deduped History:** Sync new records from the source and add them to the destination. Also provides a de-duplicated view mirroring the state of the stream in the source.

## Normalization

Normalization is the process of structuring data from the source into a format appropriate for consumption in the destination. For example, when writing data from a nested, dynamically typed source like a JSON API to a relational destination like Postgres, normalization is the process which un-nests JSON from the source into a relational table format which uses the appropriate column types in the destination.

Note that normalization is only relevant for the following relational database & warehouse destinations:

* BigQuery
* Snowflake
* Redshift
* Postgres
* Oracle
* MySQL
* MSSQL

Other destinations do not support normalization as described in this section, though they may normalize data in a format that makes sense for them. For example, the S3 destination connector offers the option of writing JSON files in S3, but also offers the option of writing statically typed files such as Parquet or Avro.

After a sync is complete, Airbyte normalizes the data. When setting up a connection, you can choose one of the following normalization options:

* Raw data (no normalization): Airbyte places the JSON blob version of your data in a table called `_airbyte_raw_<stream name>`
* Basic Normalization: Airbyte converts the raw JSON blob version of your data to the format of your destination. _Note: Not all destinations support normalization._

_Note: Custom normalization through dbt is not yet available for Airbyte Cloud._

## Workspace

A workspace is a grouping of sources, destinations, connections, and other configurations. It lets you collaborate with team members and share resources across your team under a shared billing account.

When you [sign up](http://cloud.airbyte.io/signup) for Airbyte Cloud, we automatically create your first workspace where you are the only user with access. You can set up your sources and destinations to start syncing data and invite other users to join your workspace.

## Credits

An Airbyte credit is a unit of measure used to pay for Airbyte resources when you run a sync.

What one credit stands for depends on the source type:

| **Source type**   | **What does one credit stand for?**         |
| ----------------- | ------------------------------------------- |
| API sources       | 1 hour of compute (360k rows on average)    |
| Databases         | 1/10 hour of compute (450k rows on average) |
| Files             | 1/4 hour of compute (65k rows on average)   |
| Custom connectors | 1 hour of compute (360k rows on average)    |

Compute time is the time between replicating the first and last bytes.

Credits are charged for successful syncs, normalization, and canceled jobs and attempts. Credits are not charged for failed jobs and attempts.

_Note: Credits expire after one year._

**Warning:** Since our pricing model is linear, your costs will start rising as your data needs grow. Contact us for customized pricing if you want to replicate more than 1TB of data in your databases or 50 million records across your API sources on a monthly basis.
