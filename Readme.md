# Installation

## Quickstart

If you have homebrew installed,

```zsh
brew tap kovetskiy/mark
brew install mark
```

Create a *non-scoped* API key for confluence cloud using instructions [https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

While typically using scopes is better, I have not gotten scoped tokens to work.

Create a configuration file, and place it in ~/Library/Application\ Support/mark.toml

```toml
username = "your-email"
password = "api-key-for-confluence-cloud"
base-url = "https://bridgesourcemedical.atlassian.net/wiki"
title-from-h1 = true
drop-h1 = true
space = "Space within Confluence to publish to" // example: UMDI (use the space "key")
```

If the default location is not recognized, you can put it anywhere, but you'll need to call it out with

```zsh
mark -c "/Users/johnporterfield/Library/Application\ Support/mark.toml" -f "test.md"
```

for example.

By default, the first level heading will be the title of the page.
You'll want to specify the space's name (also known as the "key"), so that mark will know where to put it.
