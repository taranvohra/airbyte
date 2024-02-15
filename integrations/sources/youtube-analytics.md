# YouTube Analytics

YouTube Analytics connector supports [YouTube Analytics Bulk Reports](https://developers.google.com/youtube/reporting/v1/reports). It retrieves bulk reports containing YouTube Analytics data for a [channel](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports) or [content owner](https://developers.google.com/youtube/reporting/v1/reports/content\_owner\_reports).

## Sync overview

YouTube does not start to generate a report until you create a [reporting job](https://developers.google.com/youtube/reporting/v1/reports#step-3:-create-a-reporting-job) for that report. Airbyte creates a reporting job for your report or uses current reporting job if it's already exists. The report will be available within 48 hours of creating the reporting job and will be for the day that the job was scheduled. For example, if you schedule a job on September 1, 2015, then the report for September 1, 2015, will be ready on September 3, 2015. The report for September 2, 2015, will be posted on September 4, 2015, and so forth. Youtube also generates historical data reports covering the 30-day period prior to when you created the job. Airbyte syncs all available historical data too.

## Features

| Feature               | Supported?  |
| --------------------- | ----------- |
| Full Refresh Sync     | Yes         |
| Incremental Sync      | Yes         |
| SSL connection        | Yes         |
| Channel Reports       | Yes         |
| Content Owner Reports | Coming soon |
| YouTube Data API      | Coming soon |

### Supported Reports

This source is capable of syncing the following reports and their data:

* [channel\_annotations\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-annotations)
* [channel\_basic\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-user-activity)
* [channel\_cards\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-cards)
* [channel\_combined\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-combined)
* [channel\_demographics\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-viewer-demographics)
* [channel\_device\_os\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-device-type-and-operating-system)
* [channel\_end\_screens\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-end-screens)
* [channel\_playback\_location\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-playback-locations)
* [channel\_province\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-province)
* [channel\_sharing\_service\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-content-sharing)
* [channel\_subtitles\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-subtitles)
* [channel\_traffic\_source\_a2](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#video-traffic-sources)
* [playlist\_basic\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-user-activity)
* [playlist\_combined\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-combined)
* [playlist\_device\_os\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-device-type-and-operating-system)
* [playlist\_playback\_location\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-playback-locations)
* [playlist\_province\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-province)
* [playlist\_traffic\_source\_a1](https://developers.google.com/youtube/reporting/v1/reports/channel\_reports#playlist-traffic-sources)

## Getting Started

* Go to the [YouTube Reporting API dashboard](https://console.cloud.google.com/apis/api/youtubereporting.googleapis.com/overview) in the project for your service user. Enable the API for your account.
* Use your Google account and authorize over Google's OAuth 2.0 on connection setup. Please make sure to grant the following [authorization scope](https://developers.google.com/youtube/reporting/v1/reports#step-1:-retrieve-authorization-credentials): `https://www.googleapis.com/auth/yt-analytics.readonly`.

## Rate Limits & Performance Considerations (Airbyte Open-Source)

* Free requests per day: 20,000
* Free requests per 100 seconds: 100
* Free requests per minute: 60

Quota usage is not an issue because data is retrieved once and then filtered, sorted, and queried within the application.

## Changelog

| Version | Date       | Pull Request                                           | Subject         |
| ------- | ---------- | ------------------------------------------------------ | --------------- |
| 0.1.0   | 2021-11-01 | [7407](https://github.com/airbytehq/airbyte/pull/7407) | Initial Release |
