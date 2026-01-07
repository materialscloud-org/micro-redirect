# micro-redirect
A simple HTML page that serves as a temporary javascript level redirect.
Intended to be used while some apps are in a "not quite finished state". 

### Usage

1. Update the index.html to point to the domain you want to redirect to.
2. Add/Update the CNAME record for this page (micro-redirect.materialscloud-org.github.io.)
3. When the app is ready, change the CNAME record to point to the new address.

### Example
Redirecting the preserved SSSP url (sssp.materialscloud.org to https://www.materialscloud.org/discover/sssp)

`index.html`
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="refresh" content="0; url=https://www.materialscloud.org/discover/sssp">
  <script>
    window.location.href = "https://www.materialscloud.org/discover/sssp";
  </script>
  <title>Redirecting…</title>
</head>
<body>
  Redirecting to <a href="https://www.materialscloud.org/discover/sssp">https://www.materialscloud.org/discover/sssp</a>…
</body>
</html>
```

CNAME record

`cname	sssp.materialscloud.org	micro-redirect.materialscloud-org.github.io.` 
The index.html will redirect on the clients browser.

when the page is finished simply change the cname record:

`cname	sssp.materialscloud.org	sssp.materialscloud-org.github.io.`

github manages all certificate issueing etc.
