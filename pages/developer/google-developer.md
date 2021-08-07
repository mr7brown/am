---
title: Google - Developer Account Configuration
permalink: google-developer.html
folder: mydoc
layout: portfolio-developer
---

## Overview

To access to Google Assistant SDK, developers need to configure a project
and their developer account settings in the Actions Console. These are the last
steps required before installing the SDK.

## Configure developer account settings

To enable access to the Google Assistant API, complete the following:

1.  Open the [Actions Console](https://console.actions.google.com/).<br>

2.  Click <b>Add/import project</b>.

3.  To create a new project, Enter your project's name in the **Project Name** field, then click **CREATE PROJECT**.

    Alternatively, if you already have an existing Google Cloud Platform project,
    you can select that project and import it.

    {% include image.html file="add-project-aog.png" alt="Example" %}

4.  If you created a new project, click the <b>Device registration</b> box near the bottom of the page.

    If you imported a previously-created project, this box will not be displayed. Instead, select the **Device Registration** tab (under **ADVANCED OPTIONS**) from the left navbar.

    {% include image.html file="device-registration-card.png" alt="Example" %}

    Keep this browser tab open. You will use it to register a device model in a later step.

5.  Enable the Google Assistant API on the project you selected (see the Terms of Service). You need to do this in the Cloud Platform Console.

    <a href="https://console.developers.google.com/apis/api/embeddedassistant.googleapis.com/overview" class="btn btn-grad">ENABLE API</a><br>

6.  Click **Enable**.

7.  You must configure the OAuth consent screen for your project in the Cloud Platform Console. Note that most fields on this page are optional.

{% include image.html file="consent-oauth_censored.png" alt="Example" %}

### Set activity controls for your account

To use the Google Assistant, you must share certain activity data with Google. The Google Assistant needs this data to function properly and is not specific to the SDK.

Open the Activity Controls page for the Google account that you want to use with the Assistant. You can use any Google account, it does not need to be your developer account.

**Ensure the following toggle switches are enabled (blue):**

* Web & App Activity
  * Be sure to select the **Include Chrome history and activity from sites, apps, and devices that use Google services** checkbox.
* Device Information
* Voice & Audio Activity
