---
uid: MO_Resource_Studio
---

# Resource Studio

The Resource Studio app helps you create and manage bookable resources efficiently. The resources can be tied to elements in the DataMiner System (e.g. devices, network interfaces, compute resources) or external entities (e.g. people, rooms, vehicles).

![Resource Studio Overview](~/solutions/images/Resource_Studio_Overview.png)

## App overview

The following pages are available in the app:

- ![Resource Pools](~/user-guide/images/Resource_Studio_Resource_Pools.png) **Resource Pools**: Allows you to **create**, **edit**, **delete**, **search**, and **filter** [resource pools](#resource-pools). You can also **assign** [resources](#resources) to resource pools, and edit [**capabilities**](#capabilities), [**capacities**](#capacities), and [**properties**](#properties) for each resource pool.

- ![Resources](~/user-guide/images/Resource_Studio_Resources.png) **Resources**: Allows you to **create** and **manage** specific [resources](#resources), and configure their **capabilities**, **capacities**, and **properties**.

- ![Capability Management](~/user-guide/images/Resource_Studio_Capability_Management.png) **Capability Management**: Here you can **create** and **manage** [capabilities](#capabilities), and assign the possible values they can have when associated with resources and resource pools.

- ![Capacity Management](~/user-guide/images/Resource_Studio_Capacity_Management.png) **Capacity Management**: Here you can **create** and **manage** [capacities](#capacities).

- ![Configuration Management](~/user-guide/images/Resource_Studio_Configuration_Management.png) **Configuration Management**: If a resource pool has **parameters** that can be defined per job in the Scheduling app, you can add those types of parameters here. You can give the configurations default values or make it mandatory to configure them upon job creation.

- ![Properties](~/user-guide/images/Resource_Studio_Properties.png) **Properties**: Allows you to manage [properties](#properties) that can be used by resources and resource pools.

- ![Sync](~/user-guide/images/Resource_Studio_Sync.png) **Sync**: Allows you to sync the resources from DataMiner Cube with the resource representations used in MediaOps. If you choose to sync them, before any changes are made, you will get a message specifying each change that will take place. After the sync, MediaOps resources will be updated to mirror the DataMiner resources.

- ![About](~/user-guide/images/Resource_Studio_About.png) **About**: Provides information on the **version** of the MediaOps package.

## Resources

The Resource Studio app allows you to create and manage resources. A resource can represent anything that involves managed use over time. Some examples of things a resource can represent include:

- A piece of network inventory managed by DataMiner, such as an **IRD**, a **cloud-based encoder**, or a **port on a switch**.

- An entire service managed by DataMiner that can be made available for use, such as an **uplink connection** with a certain bandwidth that will be available for a certain period of time.

- Anything with limited availability that is not managed by DataMiner, such as **rooms**, **people**, **vehicles**, **satellite transponder slots**, **IP addresses**, etc.

Each resource has a **concurrency** setting, which defines how many bookings of the resource can be made at the same time. By default, this is set to 1.

## Resource pools

A resource pool can be created to group a set of **interchangeable resources**. This allows users who utilize resources in other apps to refer to a pool instead of a specific resource. This makes it possible to **defer resource selection** until the resource is actually needed, instead of assigning a specific resource at booking creation.

Resources can be added to multiple pools, making them eligible for multiple purposes while keeping a single availability timeline and preventing resource conflicts.

## Capabilities

Capabilities give a **qualitative description** of a resource or pool, making it clear what it can be used for. When creating a workflow or job, users can specify the required capabilities for the resource to be used, and they can filter the resources in the system with these capability requirements in order to easily find a suitable one.

Each capability has a name and a list of values. Users can assign one or more values to a resource or a pool. Examples of capabilities include:

- Encoding: H.264, JPEG XS, JPEG 2K, etc.

- Video Format: SD, HD, UHD

- Modulation type: DVB-S, NS3, NS4

Capabilities can be assigned either to a resource or to a resource pool. If they are assigned to a resource pool, all resources in that pool will inherit the capabilities of the pool, but extra capabilities can also be added to individual resources.

![Capabilities](~/solutions/images/Resource_Studio_Capabilities.png)

## Capacities

Capacities, like capabilities, define how a resource can be used, but they are measured **numerically**. The following settings can be configured for capabilities:

- Units: The unit for the values of this capacity (MHz, Gbps, kBd, etc.).

- Min. range: The minimum value allowed for this capacity.

- Max. range: The maximum value allowed for this capacity.

- Step size: The increment that can be used to change the capacity's values.

- Decimals: The number of decimals allowed for values of this capacity.

Typical examples of capacities are bandwidths, bit rates, symbol rates, etc. When booking a resource, users book only a specific amount of capacity on the resource. If a resource has a concurrency higher than one, other jobs can still make use of the remaining capacity on that same resource. Contrary to capabilities, capacities cannot be configured on pools, but only on individual resources.

![Capacities](~/solutions/images/Resource_Studio_Capacities.png)

## Properties

Properties store extra details that do not affect resource selection.

Some examples of properties include data such as:

- Contact person

- Vendor name

- Geolocation
