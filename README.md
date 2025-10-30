# 10 Things Web Site

## Github Pages Setup

- Set up DNS CNAME record for app.10things.io to point to sandacretech.github.io.
- Navigate to Settings > Pages:
  - Set build and deployment source = deploy from a branch, branch = main, folder = / (root).
  - Set custom domain as app.10things.io and perform DNS check.
  - Once TLS certificate has been created, check Enforce HTTPS.

Now the site should be available at https://app.10things.io
