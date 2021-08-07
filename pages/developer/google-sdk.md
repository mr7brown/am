---
title: Google - SDK Installation
layout: portfolio-developer
permalink: google-sdk.html
---

## Overview

These are the instructions for installing the Google Assistant SDK and for
performing test utterances. Once the Assistant is properly embedded in the
Pi, you can begin developing customs actions that will work with your device.

### Configure Python virtual environment

Use a [Python virtual environment](https://docs.python.org/3/library/venv.html)
to isolate the SDK and its dependencies from the system Python packages.

{% include important.html content="Run all commands from the <b>/home/pi</b> directory." %}

Run the following commands for Python 3:
```
$ sudo apt-get update
$ sudo apt-get install python3-dev python3-venv
$ python3 -m venv env
$ env/bin/python -m pip install --upgrade pip setuptools wheel
$ source env/bin/activate
```

{% include important.html content="One additional set of commands is included
in this process, but it was authored by another writer, so it has bee redacted.
My documentation starts again at the <i>Complete test utterance</i> section." %}

### Complete test utterance

Now it's time to complete a test utterance. Once the utterance has been
completed successfully, you will be able to begin creating custom actions that
will work with your device.

In the command below:

1. Replace `my-dev-project` with the Google Cloud Platform project ID for the
[Actions Console](https://console.actions.google.com/) project you created.
* To find the project ID in the Actions Console, select the project, click the
gear icon, and select <b>Project settings</b>.
2. Replace `my-model` with the name of the model you created previously.
```
$ googlesamples-assistant-hotword --project-id my-dev-project --device-model-id my-model [--nickname device-nickname] [--query text-query]
```
3. Say test utterance. To initiate, say <i>Ok Google</i> or <i>Hey Google</i>,
proceeded by one of the following:
* <i>Tell me a joke.</i>
* <i>What time is it in New York?</i>
* <i>What is the record for the Golden State Warriors?</i>

If the Assistant responds, you have successfully embedded the Assistant into
your Pi!
