# Purpose

These github workflows automate the creation of JIRA tickets in AskYourTeam project backlogs when a dependabot PR is opened.

There are two configuration options to choose from depending on the ownership of your GitHub repository/application.

For shared repo's like the monorail, there is `dependabot-to-jira-randomised.yml`. This will pick a JIRA board at random to create a ticket in, hopefully sharing the pain/responsibility of actioning CVE's when they are raised by dependabot.

For repo's where maintenance responsibilities are owned by a single team, then use `dependabot-to-jira-specific-team.yml`.


## Installation instructions

To setup automated card generation within your repository, copy one of the workflow yml files into your source code `.github/workflows/` folder.

## Troubleshooting

These actions rely on the following variables being set:

```yaml
  vars.JIRA_BASE_URL
  vars.JIRA_USER_EMAIL
  vars.JIRA_ISSUE_TYPE
  vars.JIRA_PROJECT_KEY_CHARLIES
  vars.JIRA_PROJECT_KEY_PHOENIX
```

These should be defined within our GitHub account's organisation level variables defined here: https://github.com/organizations/askyourteam-nz/settings/variables/actions

Both files also require the presence of the following "dependabot" secrets:

```yaml
  secrets.JIRA_API_TOKEN
```

These are not defined within the organisation secrets area, but are actually set here within dependabot secrets: https://github.com/organizations/askyourteam-nz/settings/secrets/dependabot
