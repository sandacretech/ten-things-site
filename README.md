# 10 Things Web Site

## Github Pages Setup

- Set up DNS CNAME record for app.10things.io to point to sandacretech.github.io.
- Navigate to Settings > Pages:
  - Set build and deployment source = deploy from a branch, branch = main, folder = / (root).
  - Set custom domain as app.10things.io and perform DNS check.
  - Once TLS certificate has been created, check Enforce HTTPS.

Now the site should be available at https://app.10things.io

## Hugo

The [Hugo](https://gohugo.io/) static site generator is used to create this web site. Please install the `hugo` binary for development. You will also need to install [Go](https://go.dev/) to treat the theme as a module (see below).

### Initial Setup

The following steps were followed to set this site up:

    $ hugo new site ten-things-site
    $ cd ten-things-site
    $ hugo mod init ten-things-site

### Development

To start the development server:

    $ hugo server

The `/content/*.md` files can be edited and the server will auto refresh the page.

### Theme

The [Hyde](https://github.com/spf13/hyde) theme will automatically be installed as a hugo module when the server is started. See [this post](https://www.nickgracilla.com/posts/master-hugo-modules-managing-themes-as-modules/) for more information.

Configuration options for `hugo.toml` are documented on the theme's [github page](https://github.com/spf13/hyde). Relevant html files were copied from the theme's `layouts` directory into `/layouts` and edited to customise the theme.
