## Applying Filter in List API

* `per-page`: specifies the maximum number of items to return. The value must be an integer. If the per-page is not specified, the system returns 20 matches.
* `page`: specifies the current page.
* `filter`: specifies filter which should be in JSON format

**Example List Request URL**

```
/api/pim/product?page-page=20&page=1&filter={"status": "enable"}
```
