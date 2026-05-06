---
uid: Web_apps_Feature_Release_10.6.7
---

# DataMiner web apps Feature Release 10.6.7 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

This Feature Release of the DataMiner web applications contains the same new features, enhancements, and fixes as DataMiner web apps Main Release 10.6.0 [CU4].

> [!TIP]
>
> - For release notes related to the general DataMiner release, see [General Feature Release 10.6.7](xref:General_Feature_Release_10.6.7).
> - For release notes related to DataMiner Cube, see [DataMiner Cube Feature Release 10.6.7](xref:Cube_Feature_Release_10.6.7).

## Highlights

*No highlights have been added yet.*

## New features

#### GQI DxM - Extensions: Retrieving the Culture and Timezone from the Session object [ID 45348]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

Within a GQI extension, it will now be possible to retrieve the *Culture* and *Timezone* from the `Session` object. When the `IGQIOnInit` interface is implemented, the `Session` object is a property of `OnInitInputArgs`.

> [!NOTE]
> For this new feature to work, the extension needs to be created with the `Skyline.DataMiner.Core.GQI.Extensions` NuGet (version 1.1.0 or above). The feature is not supported when the extension is created using the `SLAnalyticsTypes` API.

## Changes

### Enhancements

#### Low-Code Apps: Enhanced performance when loading pages and panels [ID 45365]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

Because of a number of enhancements, overall performance has increased when loading pages and panels of low-code apps.

#### DataMiner Web Services API v0 has now been removed [ID 45387]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

The DataMiner Web Services API v0 was declared End of Life in DataMiner version 10.1.5. It has now been removed from the code base.

> [!IMPORTANT]
> It will no longer be possible to enable the v0 interface by setting the `enableLegacyV0Interface` key to true in the `C:\Skyline DataMiner\Webpages\API\Web.config` file.

### Fixes

#### Dashboards/Low-Code Apps - Interactive automation scripts: Redesigned controls would incorrectly not allow you to use the arrow keys to move the cursor [ID 45313]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

When, in a dashboard or a low-code app, an interactive automation script was launched in a popup window, the redesigned controls would incorrectly not allow you to use the arrow keys to move the cursor.

For example, when you pressed the *Up*/*Down* arrow in a multi-line textbox, the cursor would incorrectly not move to the previous/next line.

#### Dashboards/Low-Code Apps: Problem with 'Data used in ...' sections [ID 45373]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

When you open a dashboard or a low-code app, the *Data used in dashboard/page/panel* section of the *Data* pane will list all data items used in the dashboard or low-code app page or panel, such as data sources, filters, and more, and when you select a particular component, the *Data used in component* section of the *Data* pane will list all data items used in the currently selected component.

However, up to now, because of a filtering issue, in some cases, these sections would not list the correct data items.

#### Monitoring app: List of available pages in an element card would incorrectly include a 'Dashboards' page when the LegacyReportsAndDashboards option was disabled [ID 45420]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

In the *Monitoring* app, up to now, the list of available pages in an element card would incorrectly include a *Dashboards* page when the *LegacyReportsAndDashboards* soft-launch option was disabled.
