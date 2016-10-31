---
title: Configure Access for GitHub Repositories
tags:
keywords: ""
last_updated: "October 30, 2016"
summary: How to add a git ssh key to CloudCoreo WebUI to access private GitHub repositories.
published: true
sidebar: faq_sidebar
permalink: faq_add_git_ssh_key.html
folder: faq
toc: false
---

### Details  
The CloudCoreo WebUI can access Composites that are kept in private Github repositories. This is possible when your private SSH key for Github is added to the CloudCoreo WebUI. You must have a CloudCoreo Pro account to be able to add private git keys to the CloudCoreo WebUI.

### Adding a git ssh private key to CloudCoreo WebUI  

To configure CloudCoreoWebUI to access private Github repositories perform the following:


1.  Generate SSH keys (skip to step 3. if you have already done this)
    1. Follow instructions:[Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

2.  Add public key to GetHub (skip to step 3. if you have already done this)
    1. Follow GitHub's instructions: [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) 

3.  Add your git private ssh key to CloudCoreo WebUI
    1. In CloudCoreo WebUI, select Settings from the left navigation bar. 
    2. Click the Git Keys tab.
    3. Click the ADD NEW button.
    4. Type in a name for the Key Name.
    5. Copy and paste the Private Key Material; this is the content of the private key typically found in their default location, which can be accessed using the following command: cat ~/.ssh/id_rsa.  The default name id_rsa may need to be replaced with the particular private key used with the desired GitHub account if it is different from the default.
    6. If the Private Key format is correct, the ADD button will become clickable.
    7. Click ADD. If successful, the fingerprint for the key should now appear with its title  
