---
title: Configure Access for GitHub Repositories
tags:
keywords: ""
last_updated: "October 30, 2016"
summary: Configuring SSH keys for Accessing GitHub Repositories
published: true
sidebar: mydoc_sidebar
permalink: mydoc_setup-github-key.html
folder: mydoc
toc: false
---

### Details  
CloudCoreo WebUI can automatically access private Github repositories and use them as "composites". CloudCoreo WebUI accesses GitHub repositories by using a private SSH key; the corresponding public key is registered with the targeted GitHub private account.

### Procedure  

To configure CloudCoreoWebUI to access private Github repositories perform the following:


1.  Generate SSH keys (skip to step 3. if you have already done this)
    1. Follow instructions:[Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

2.  Add public key to GetHub (skip to step 3. if you have already done this)
    1. Follow GitHub's instructions: [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) 

3.  Add private key to CloudCoreo WebUI
    1. In CloudCoreo WebUI in the navigation bar select Settings
    2. Select Git Keys
    3. Use the ADD NEW button
    4. Provide an identifying Key Name
    5. Provide the Private Key Material; this is the content of the private key typically found in their default location, which can be accessed using the following command: cat ~/.ssh/id_rsa.  The default name id_rsa may need to be replaced with the particular private key used with the desired GitHub account if it is different from the default.
    6. If the Private Key format is correct, the ADD button well becomes selectable
    7. Select ADD, the fingerprint for the key should now appear with its title  
