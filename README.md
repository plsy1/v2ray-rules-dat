## Changes

- Add `geosite:douyin`

- Add `https://raw.githubusercontent.com/217heidai/adblockfilters/main/rules/adblockqxlite.conf` to `geosite:category-ads-all`

See direct.txt and reject.txt in the hidden branch for other changes.

## Structure of data

All data are under `data` directory. Each file in the directory represents a sub-list of domains, named by the file name. File content is in the following format.

```
# comments
include:another-file
domain:google.com @attr1 @attr2
keyword:google
regexp:www\.google\.com$
full:www.google.com
```

**Syntax:**

> The following types of rules are **NOT** fully compatible with the ones that defined by user in V2Ray config file. Do **Not** copy and paste directly.

* Comment begins with `#`. It may begin anywhere in the file. The content in the line after `#` is treated as comment and ignored in production.
* Inclusion begins with `include:`, followed by the file name of an existing file in the same directory.
* Subdomain begins with `domain:`, followed by a valid domain name. The prefix `domain:` may be omitted.
* Keyword begins with `keyword:`, followed by a string.
* Regular expression begins with `regexp:`, followed by a valid regular expression (per Golang's standard).
* Full domain begins with `full:`, followed by a complete and valid domain name.
* Domains (including `domain`, `keyword`, `regexp` and `full`) may have one or more attributes. Each attribute begins with `@` and followed by the name of the attribute.

> **Note:** Adding new `regexp` and `keyword` rules is discouraged because it is easy to use them incorrectly, and proxy software cannot efficiently match these types of rules.
