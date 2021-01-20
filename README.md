# jira-me-timbers
Configuration and scripts for `go-jira` cli.


## Prerequisites

The [jira cli](https://github.com/go-jira/jira) tool needs to be available on your path. You can install it with:

```
brew install go-jira
```

## Installation

Copy the `.jira.d` directory into your `~/`. 

```sh
cp -r .jira.d ~/
```

In `~/.jira.d/config.yml` you must replace:

* `<JIRA_ENDPOINT>` with your Jira URL.
* `<JIRA_USERNAME>` with your Jira username.
* `<PRJT>` with your JIRA project code, e.g. `ADMN`. The project field is optional and can be removed if you don't want to filter by it.

Run `jira list` to begin authentication with the jira server. You will need to create an API token which can be done [here](https://id.atlassian.com/manage-profile/security).

## Scripts

Along side the default commands `jira` tool provides (see `jira help`) we have introduced custom scripts:

* `jira mine` - Prints all jira tickets which are assigned to you.
* `jira mine-current` - Prints all jira tickets which are assigned to you and are in `In progress` or `In review`.
* `jira stash` - Moves all current tasks into `To do` and saves a record.
* `jira unstash` - All stashed tasks into `In progress`.
