# 10 Things Web Site

## Github Pages Setup

- Set up DNS A records for 10things.io:
  - 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
  - See https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain
  - Note that this is different to setting up a subdomain with a CNAME record.
- Navigate to Settings > Pages:
  - Set build and deployment source = deploy from a branch, branch = main, folder = /docs.
  - Set custom domain as app.10things.io and perform DNS check.
  - Once TLS certificate has been created, check Enforce HTTPS.

Now the site should be available at https://10things.io

## Hugo

The [Hugo](https://gohugo.io/) static site generator is used to create this web site. Please install the `hugo` binary for development. You will also need to install [Go](https://go.dev/) to treat the theme as a module (see below).

### Initial Setup

The following steps were followed to set this site up:

    $ hugo new site ten-things-site
    $ cd ten-things-site
    $ hugo mod init ten-things-site

### Theme

The [Hyde](https://github.com/spf13/hyde) theme will automatically be installed as a `hugo` module when the server is started. See [this post](https://www.nickgracilla.com/posts/master-hugo-modules-managing-themes-as-modules/) for more information.

Configuration options for `hugo.toml` are documented on the theme's [github page](https://github.com/spf13/hyde). Relevant html files were copied from the theme's `layouts` directory into `/layouts` and edited to customise the theme.

### Development Server

To start the development server:

    $ hugo server

The `/content/*.md` files can be edited and the server will auto refresh the page.

### deployment

To build the site, run:

    $ hugo build
    $ git push origin main

This will place the static site into the `/docs` directory. The `git push` to github will set off the automatic deployment.
