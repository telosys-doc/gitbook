# GitHub usage

## GitHub depot configuration

It's possible to define 3 types of depot:

* a GitHub organization:  \
  &#xNAN;**`github_org`**  + "**`:`** " + _**`organization-name`**_
* a GitHub user: \
  &#xNAN;**`github_user`**  + " **`:`**" + _**`user-name`**_
* the GitHub current user (authenticated by the current personal acces token): \
  &#xNAN;**`github_current_user`**&#x20;

To define your own depots on GitHub see "[Project configuration](../configuration-and-variables.md)".



## GitHub Personal Access Token

Telosys uses the GitHub REST API ( [https://docs.github.com/en/rest](https://docs.github.com/en/rest) ) to get the models or bundles available for installation.

This API has “rate limits” which can be reached quite quickly if several users share the same external IP address (which is usually the case with a corporate proxy).

To get around this limitation, you can use a "**GitHub Personal Access Token**" (PAT).

With a "Personal Acces Token" the limit increased from 50 to 5000 requests for each user with a token.

Since version 4.2.0 you can use the command "**ght**" ("GitHub Token") to define (or remove) a "Personal Acces Token" that Telosys will use to call the GitHub API.

**Step 1 - Define your Personal Acces Token in GitHub**&#x20;

See GitHub documentation : "[Managing your personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)"

Creating a personal access token (classic) is sufficient

**Step 2 - Use your Personal Acces Token with Telosys**

Once you have your token, you can use the “**ght**” command to store it on your workstation. \
The token is encrypted and stored locally, so it can be used for all Telosys projects on a workstation.

* Check if the token is defined :  **`ght`**
* Define a token:   **`ght -set`**  ⇒ Copy/Paste your token&#x20;
* Remove the token:   **`ght -none`**

