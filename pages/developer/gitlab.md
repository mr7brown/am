---
title: HBO - GitLab Set Up
permalink: gitlab.html
folder: mydoc
layout: portfolio-developer
---

## Overview

{% include important.html content="This guide assumes that you have access to HBO's GitLab instance and have installed the Gatsby CLI." %}

This guide provides instructions for establishing a connection with the GitLab repo for the Partner Hub. By the end, you will:

1. Clone the `/partnerhub/web` repo.
2. Validate SSH key pair.
3. Push a test commit.

After successfully pushing a test commit, you can begin contributing to the Partner Hub.

## Clone the Partner Hub Repo

To begin, you need to clone the `/partnerhub/web` repo. From your terminal, run the following command:

```
$ git clone git@git.REDACTED:/partnerhub/web.git
```

After cloning the repo, go to the [Submit Test Commit](/gitlab.html#submit-test-commit) section. If your account was provisioned correctly, you should be able to make commits without additional setup. If you are unable to make a test commit, continue to the next section to establish a key pair.

## Working with GitLab and SSH keys

HBO's GitLab instance requires an SSH connection instead of the traditional HTTPS connection. The following sections provide instructions for generating an SSH key and adding it to your GitLab profile.

Gitlab's [SSH Key](https://git.wmedia.tech/help/ssh/README#generating-a-new-ssh-key-pair) guideline contains more information on the commands behind key generation.

### SSH key generation

To generate a new SSH key:

1. Open a terminal and run:
```
# Use your desktop account
$ ssh-keygen -t ed25519 -C "email@example.com"
```
2. Follow the prompts to continue (it is recommended that you enter a password for an extra layer of security).

### Adding SSH key to GitLab

1. To copy your SSH key, run:
```
$ pbcopy < ~/.ssh/id_ed25519.pub
```
2. Navigate to **SSH Keys** (link has been redacted) in your GitLab **User Settings**.
2. Paste your copied key in the text box, it should look something like this: `47:xf:71:x7:02:1x:7x:x9:9x:x3:xx:7x:xx:6x:0x:xx`. 
3. Enter a descriptive title and click **Add key**.

## Testing connection

To test if you correctly added an SSH key to your GitLab profile, run:
```
# The actual GitLab instance has been redacted.
$ ssh -T git@gitlab.com
```

If this is the first time connecting to the GitLab instance you will be prompted with a message asking you to continue, answer `yes` to add GitLab to the list of trusted hosts. If successful, you should receive a Welcome to GitLab, `@username`! message.

With the connection validated, you should be able to add commits to the `/partnerhub/web` repo. The last step is to submit a test commit!

## Submit test commit

`src/content/test` allows you to test your connection to the GitLab instance without impacting QA or Production environments. To test your connection:

1. Run:
```
$ git checkout -b test
```

2. Create a Markdown file with your username as the title `<user@hbo.md>` in the `src/content/test/` folder.
3. Commit changes :
```
$ git add <filename>
$ git commit -m "<commit message>"
$ git push 
```
4. Once successful, use the link in the terminal to create a merge request. All merge requests should be assigned to **REDACTED**.

Congratulations, you just made your first commit, and can now begin contributing to the HBO code base!