# announcements
Announcements to display in dApps.

The `announcements.json` file from this repo is intended to be consumed by the dApps to be able to display announcements so that they are not hardcoded into the frontend codebase.

Currently the announcement data model supports the following properties:
- `text`: the content of the announcement
- `urlText`: the text content of where the announcement links to (optional)
- `url`: the URL where the announcement links to (optional)
- `timing`: 
  - `from`: a datetime string in ISO format, the time when the announcement should show (optional)
  - `to`: a datetime string in ISO format, until when the announcement should be alive (optional)

The announcements json would take a list of these announcement models for each dApp:

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
  "wallet": []
}

```
