# netlify-plugin-no-more-404 Demo

Experimenting with the plugin architecture to run Axe checks on Netlify sites

Example site: https://netlify-plugin-no-more-404.netlify.com
Logs: 

This demonstrates use of the following Netlify Plugins:

- [netlify-plugin-no-more-404](https://github.com/sw-yx/netlify-plugin-no-more-404)

## Usage

Instructions for running a version of this demo site for yourself.

```bash

# clone the repo
git clone https://github.com/sw-yx/netlify-plugin-no-more-404

# move into working directory and install dependencies
cd netlify-plugin-no-more-404
npm install

# ensure that you have the netlify build command available
# (in future this will be provided via the CLI)
npm install @netlify/build -g

# run the build as netlify would with the build bot
netlify-build
```

## The Netlify Config

This is how the config is set up.

```yaml
plugins:
  plugin-nomo404:
    type: netlify-plugin-no-more-404
    config:
      site: mycoolsite.netlify.com # your Netlify site url
      # https://github.com/dequelabs/axe-cli#running-specific-rules
      axeFlags: --rules color-contrast,html-has-lang
```

## Known issues

- `netlify api updateSite --data='{ "site_id": "418b94bc-...", "body": { "netlify_build_enabled": true  }}'`
- tbc