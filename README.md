# announcements
Announcements to display in vega frontends.

The `announcements.json` file from this repo is intended to be consumed by the dApps to be able to display announcements so that they are not hardcoded into the frontend codebase.

### Announcement model

Currently the announcement data model supports the following properties:
- `text`: the content of the announcement
- `urlText`: the text content of where the announcement links to (optional)
- `url`: the URL where the announcement links to (optional)
- `timing`: 
  - `from`: a datetime string in ISO format, the time when the announcement should show (optional)
  - `to`: a datetime string in ISO format, until when the announcement should be alive (optional)

### Applications

The announcements json would take a list of these announcement models for each (d)app (`console`, `governance`, `explorer`, `wallet`, `website`):

```
{
  "console": [{
    "text": "Listen up!",
    "urlText": "Click this",
    "url": "vega.xyz",
    "timing": {
      "from": "2018-11-13T20:20:39+00:00",
      "to": "2028-11-13T20:20:39+00:00"
    }
  }],
  "governance": [...],
  "explorer": [...],
  "wallet": [],
  "website": []
}

```

To consume the announcement data and display it on the frontend, the vega apps use this react library: [@vegaprotocol/announcements](https://www.npmjs.com/package/@vegaprotocol/announcements)

### Environments

To display different announcements in different network environments, we use branches, and point the announcement configuration url to the raw json file for the branch. 

Environment specific branches, which are supposed to be long-lived:
- [mainnet](https://github.com/vegaprotocol/announcements/tree/mainnet)
- [fairground](https://github.com/vegaprotocol/announcements/tree/fairground)
- [develop](https://github.com/vegaprotocol/announcements/tree/develop)
- [main](https://github.com/vegaprotocol/announcements/tree/main)



