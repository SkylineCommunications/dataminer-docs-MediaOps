---
uid: Cube_Feature_Release_10.6.7
---

# DataMiner Cube Feature Release 10.6.7 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

This Feature Release of the DataMiner Cube client application contains the same new features, enhancements, and fixes as DataMiner Cube Main Release 10.6.0 [CU4].

> [!TIP]
>
> - For release notes related to the general DataMiner release, see [General Feature Release 10.6.7](xref:General_Feature_Release_10.6.7).
> - For release notes related to the DataMiner web applications, see [DataMiner web apps Feature Release 10.6.7](xref:Web_apps_Feature_Release_10.6.7).

## Highlights

*No highlights have been selected yet.*

## New features

*No features have been added yet.*

## Changes

### Enhancements

#### Settings: Increased responsiveness of the Search box [ID 44956]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

Because of a number of enhancements made to the *Settings* window, the responsiveness of the *Search* box has increased.

### Fixes

#### Alarm Console: Problem when detecting recursive loops in nested correlation alarms [ID 45372]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

Because of a problem with the recursive loop detection mechanism, in some cases, a recursive loop in nested correlated alarms could still cause DataMiner Cube to stop working unexpectedly.

#### Services: Problem with element selector filter box [ID 45378]

<!-- MR 10.5.0 [CU16] / 10.6.0 [CU4] - FR 10.6.7 -->

When you are adding elements to a service using the element selector, a filter box allows you to narrow down the number of elements listed in that selector. Since the most recent redesign of the DataMiner Cube UI, part of that filter box would incorrectly be cut off.

This same issue would also occur when adding primary and backup elements to a redundancy group, when creating an alarm filter in the Alarm Console, and when assigning elements to a connector.
