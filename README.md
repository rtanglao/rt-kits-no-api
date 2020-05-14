# rt-kits-no-api
miscellaneous kitsune aka support.mozilla.org stuff that doesn't have an API

## 14may2020 how to get the relative URLs

```bash

curl "https://support.mozilla.org/en-US/contributors/kb-overview?product=firefox" | \
pup '#kb-overview-table tbody tr td:nth-child(1) a[href*="/en-US/kb/"]['href']' \
| grep -o '/en-US/[^\"]*' > all_relative_desktop_urls.html
```
