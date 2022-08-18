---
title: MoEngage (Actions) Destination
cmode-override: true
id: 55b280290a20f4e22f0fb3d6
hide-personas-partial: true
hide-boilerplate: true
hide-dossier: true
---

<!-- This template is meant for Actions-based destinations that represent a new version of an existing, or Classic Segment destination. For new Actions-based destinations, see the doc-template-new.md template -->

<!-- In the section above, edit the `title` field. For example, Slack (Actions) Destination -->

{% include content/plan-grid.md name="actions" %}

<!-- Include a brief description of the destination here, along with a link to your website. -->

<!-- In the section below, add your destination name where indicated. If you have a classic version of the destination, ensure that its documentation is linked as well. If you don't have a classic version of the destination, remove the second and third sentences. -->

> success ""
> **Good to know**: This page is about the [Actions-framework](/docs/connections/destinations/actions/) <destination_name> Segment destination. There's also a page about the [non-Actions <destination_name> destination](/docs/connections/destinations/catalog/moengage/). Both of these destinations receives data from Segment.

<!-- This include describes the requirement of A.js 2.0 or higher for Actions compatibility, and is required if your destination has a web component. -->

{% include content/ajs-upgrade.md %}

<!-- In the section below, explain the value of this actions-based destination over the classic version, if applicable. If you don't have a classic version of the destination, remove this section. -->

## Benefits of MoEngage (Actions) vs MoEngage Classic

MoEngage (Actions) provides the following benefits over the MoEngage Classic destination:

<!-- rephrase slack for mapping and config -->
- **Data Consistency**. Data consistency between device mode and cloud mode. Earlier, data sent from device and cloud mode would sometimes be mismatched with duplicated properties - this has now been fixed.
- **Better Mapping**. Using MoEngage Actions, you can now map incompatible properties with MoEngage-compatible properties. This will significantly reduce your development bandwidth. 
- **Region Support**. Support across all data clusters. We now provide an option to choose your Data Region where your app is present.
- **Better Configuration**. Additional configurations for JS integration like custom Service Worker, etc.

<!-- The section below explains how to enable and configure the destination. Include any configuration steps not captured below. For example, obtaining an API key from your platform and any configuration steps required to connect to the destination. -->

## Getting started

1. From the Segment web app, click **Catalog**, then click **Destinations**.
2. Find the Destinations Actions item in the left navigation, and click it.
3. Click **Configure MoEngage**.
4. Select an existing Source to connect to MoEngage (Actions).
5. Finish the setup.
6. Configure the settings. See the table below for more information.
7. Enable the toggle option to Enable destination and click Save changes. 


Field Name | Description |
---------|----------|
 Name | Name of the moengage destination such as MoEngage prod, MoEngage test, etc. |
 App Id | Navigate to Settings >> API >> General on your MoEngage dashboard and copy paste the App ID. |
 App Key  | Navigate to Settings >> API >> General on your MoEngage dashboard and copy paste the App Key. |
 Endpoint Region | This is your MoEngage data center. [Read more](https://help.moengage.com/hc/en-us/articles/360057030512-Data-Centers-in-MoEngage) |

<!--
Additional Context

Include additional information that you think will be useful to the user here. For information that is specific to an individual mapping, please add that as a comment so that the Segment docs team can include it in the auto-generated content for that mapping.
-->

### Correctly mapping User ID and Anonymous ID

For correctly resolving the User Identification, please make sure you fill in the values that MoEngage expects. Scroll down to "Define mappings" section and change the following keys from sentence case to Camel Case. Make sure you select the new values from the dropdown. 

Key | Default Value | New Value 
---------|----------|---------
 User ID | `user_id` | `userId`
 Anonymous ID | `anonymous_id` | `anonymousId`

<!-- The line below renders a table of connection settings (if applicable), Pre-built Mappings, and available actions. -->

{% include components/actions-fields.html %}
 
## Testing the integration

1. Go to Event tester tab on the segment dashboard.
2. Test for Track and Identify methods and make sure that you are getting success status here.

![Event Tester](images/EventTester.png)

If successful the data would start flowing into your MoEngage account in 3-5 minutes. You can login to your MoEngage dashboard and go to Test & Debug >> Recent events to verify. 

<!-- If applicable, add information regarding the migration from a classic destination to an Actions-based version below -->

## Migration from the classic MoEngage destination

{% include content/ajs-upgrade.md %}

Follow the table below to map your existing MoEngage destination configuration to MoEngage (Actions).

{% include components/actions-map-table.html name="moengage" %}