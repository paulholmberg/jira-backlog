# jira-backlog

jira-backlog is a set of javascript libraries that create a custom view into the backlog of an existing JIRA Board. The intent behind the creation of this view is to enable Product Owners to draw the link between a Story Point estimated backlog and time, while keeping that link malleable. It is designed to facilitate crucial conversations with the development team and with stakeholders, supporting what-if scope changes and exploration of the why behind certain dates.

## Getting Started

### Prerequisites

jira-backlog is built to be embedded in a Confluence page and as such requires a Confluence and a JIRA instance.

The two deployments must be [linked](https://confluence.atlassian.com/doc/integrating-jira-and-confluence-2825.html#IntegratingJiraandConfluence-ConnectJiraandConfluencewithanapplicationlink) (ie you can embed and create JIRA tickets in Confluence pages)

In addition you must have the [HTML Macro](https://bobswift.atlassian.net/wiki/spaces/HTML/pages/6422530/HTML+Macro) plugin installed, and support for including javascript enabled.

### Installing

Embed an HTML macro on your Confluence page and configure the 'Location of HTML Data' field to the following:

```
#https://paulholmberg.github.io/jira-backlog/embed_me.html
```

Include in the body of the macro a brief snippet of javascript to set up the default variables for this page:

```
<script>
// Defines the board to display the backlog for
// Must match the board name as it is in JIRA exactly
var board_name = "My Example Board";

// Team velocity in story points per sprint
// The sprint length will be derived from the currently active sprint
var velocity = 50;

// The backlog view will be limited by the board filter
// You can optionally include additional JQL to further restrict the view
// Set to an empty string to disable
// For example, to exclude sub tasks:
var extra_filter_args = "issuetype!=Sub-task";
</script>
```

## Built With

* [D3js](https://d3js.org/) - The data visualisation framework

## License

This project is licensed under GPL3 - see the [LICENSE.md](LICENSE.md) file for details
