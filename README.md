# rt-kits-no-api
miscellaneous kitsune aka support.mozilla.org stuff that doesn't have an API

## 02July2020 paid product urls

```bash
curl "https://support.mozilla.org/en-US/contributors/kb-overview?product=firefox-private-network-vpn" |
pup '#kb-overview-table tbody tr td:nth-child(1) a[href*="/en-US/kb/"] attr{href}' >all_vpn_urls.html
```

## 14may2020 better solution using attr[href]
* see http://rolandtanglao.com/2020/05/14/p2-how-to-get-all-firefox-desktop-urls-using-pup-without-grep/

```bash
curl "https://support.mozilla.org/en-US/contributors/kb-overview?product=firefox" |\
pup '#kb-overview-table tbody tr td:nth-child(1) a[href*="/en-US/kb/"] attr{href}' \
> all_relative_desktop_urls.html
```

## 14may2020 how to get the relative URLs

```bash

curl "https://support.mozilla.org/en-US/contributors/kb-overview?product=firefox" | \
pup '#kb-overview-table tbody tr td:nth-child(1) a[href*="/en-US/kb/"]['href']' \
| grep -o '/en-US/[^\"]*' > all_relative_desktop_urls.html
```
