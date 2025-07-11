---
uid: Web_apps_Feature_Release_10.5.9
---

# DataMiner web apps Feature Release 10.5.9 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

This Feature Release of the DataMiner web applications contains the same new features, enhancements, and fixes as DataMiner web apps Main Release 10.4.0 [CU18] and 10.5.0 [CU6].

> [!TIP]
>
> - For release notes related to the general DataMiner release, see [General Feature Release 10.5.9](xref:General_Feature_Release_10.5.9).
> - For release notes related to DataMiner Cube, see [DataMiner Cube Feature Release 10.5.9](xref:Cube_Feature_Release_10.5.9).

## Highlights

*No highlights have been selected yet.*

## New features

#### Low-Code Apps: Using script output in the post actions of a 'Launch a script' action [ID 43222]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

The output of an Automation script can now be used in the post actions of a *Launch a script* action.

If a referenced key does not exist in the output, it will by default return an empty string.

Actions will now be numbered hierarchically to allow easier referencing when linking output data. See the example below.

- 1

  - 1.1

    - 1.1.1

  - 1.2

    - 1.2.1
    - 1.2.2

      - 1.2.2.1

- 2

## Changes

### Enhancements

#### Interactive Automation scripts: Minimum and Maximum properties of the time components will now be considered to be either local time or UTC time [ID 43014]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

In time components like e.g. `DateTimePicker` and `TimePicker`, input can be limited by means of the `Minimum` and `Maximum` properties.

Up to now, when the client machine and the server were located in different timezones, the datetime values in those two properties would not always be consistent. From now on, the values in the `Minimum` and `Maximum` properties will be considered to be either local time or UTC time according to the [DateTimeKind](https://learn.microsoft.com/en-us/dotnet/api/system.datetimekind?view=netframework-4.8), specified using [SpecifyKind](https://learn.microsoft.com/en-us/dotnet/api/system.datetime.specifykind?view=netframework-4.8).

`DateTimeKind` can be set to one of the following values:

| Value | Description |
|-------|-------------|
| Undefined | Minimum and Maximum will be used as is, regardless of the client time zone. (former behavior) |
| Local     | Minimum and Maximum will be considered to be the local time of the server. |
| Utc       | Minimum and Maximum will be considered to be UTC time. |

> [!NOTE]
> If, for the `TimePicker` component, you set the `DateTimeKind` of the `Maximum` value to either "Local" or "Utc", the `Maximum` value may roll over to the next day, causing the hour/minute value of the `Maximum` property to be lower than the hour/minute value of the `Minimum` property. Hence, all values will be invalid.

#### DataMiner landing page: Redesigned app sections [ID 43115] [ID 43226]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

The app sections on the DataMiner landing page (e.g. `https://myDMA/root/`) have been redesigned.

- In the upper section, you will find the native DataMiner apps like Dashboards, Monitoring, and Cube.
- In the lower section, you will find the apps you downloaded from the DataMiner Catalog as well as the low-code apps you create yourself (in different tabs per category).

  Click *Browse catalog* to open the [DataMiner Catalog](https://catalog.dataminer.services/) or *Create app* to create a low-code app.

### Fixes

#### Dashboards app & Low-Code Apps - Timeline component: Group label tooltips missing [ID 43242]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

When, in a *Timeline* component, you had grouped on multiple columns, only the labels of the bottom-level group would have a tooltip.

From now on, all group labels will have a tooltip.

#### Low-Code Apps: Actions on open panels would stop working when you switched from one page to another [ID 43256]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

When you switched from one page to another, up to now, actions on open panels would stop working.

#### Dashboards app & Low-Code Apps - Table component: Run-time error could appear when multiple queries had been configured [ID 43262]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

When, in a *Table* component with multiple queries, you rapidly switched between the different queries or generated a PDF, in some cases, the following run-time error could appear instead of the actual table data:

`Cannot read properties of undefined (reading "Value")`

#### Low-Code Apps - Interactive Automation script component: Input box values would not be updated correctly [ID 43282]

<!-- MR 10.4.0 [CU18] / 10.5.0 [CU6] - FR 10.5.9 -->

When the redesigned UI components were used in an Interactive Automation script component, in some cases, input box values would not be updated correctly, especially when a negative value was changed into a positive value.

Currently, by default, the existing components will still be used by default to keep the UI aligned. If you want to use the new components, then add the following argument to the URL of the low-code app:

`?useNewIASInputComponents=true`
