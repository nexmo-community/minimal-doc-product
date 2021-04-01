# minimal-doc-product

## Overview

*Minimal doc product* is a starter repository designed to help you bootstrap your own documentation project. It provides a minimal set of configuration files and content for the custom landing pages and for the Heroku pipeline.

## How to use

### To use as the starting point for your own product

If you want to use this repository as the starting point for your own documentation product, **fork** this repository on GitHub by clicking on the <kbd><b>Fork</b></kbd></a> button (Top-Right).

> **NOTE:** It is recommended you periodically [check for changes](https://rick.cogley.info/post/update-your-forked-repository-directly-on-github/) to the upstream project to make sure your repository is up to date with fixes and changes.

### To run locally

> **NOTE:** Commands are to be executed in a suitable shell on Linux, Mac, or Windows (using Powershell)

1. Clone the repo:

   ```sh
   $ git clone https://github.com/nexmo-community/minimal-doc-product.git
   ```

2. Navigate to the cloned directory:

   ```sh
   $ cd minimal-doc-product
   ```

3. Check the `Gemfile` for to select the correct Ruby version for your environment:

   - using `rbenv` (you can install `rbenv` on Mac with `brew install rbenv`):

   ``` sh
   $ rbenv 2.7.2
   $ rbenv local 2.7.2
   ```

   - or, using `rvm`:

   ``` sh
   $ rvm install 2.7.2
   $ rvm use 2.7.2 
   ```

4. Run `bundle install` to install the dependencies.

5. Run `station`:

   ``` sh
   $ OAS_PATH="`pwd`/_open_api/api_specs/definitions" bundle exec nexmo-developer --docs=`pwd`
   ```

6. In your web browser, navigate to `localhost:3000` to display the documentation landing page.

7. Add content and modify the configuration to create custom landing pages. You can also replace logos to match your product.

> **NOTE:** Some directories must be kept. If they are currently empty, they are preserved by the `.gitkeep` files.

## Setting up Heroku

To build and publish your documentation project, you need to set up a Heroku pipeline. A Heroku `app.json` file is included in the repository. Note that there are two Heroku pipelines available for your reference: `minimal-doc-product` and for  `nexmo-developer`.

To set a new pipeline, follow these steps:

1. In your GitHub repo, give admin access to the Automation team NexmoDev.
2. On Heroku, create a [new pipeline](https://devcenter.heroku.com/articles/pipelines).
3. For your pipeline, enable Review Apps.
4. Configure URL pattern to be `name-of-repo` plus PR number, for example: `minimal-doc-product-pr-123.herokuapp.com`.
5. Set the app config variables.
6. Submit a PR and ensure the review app is building.
7. Create a staging application for the pipeline.

> **IMPORTANT:** **The pipeline will be automatically deleted,** if you don't have a staging or production app and there are no review apps when the last PR is merged. To ensure your pipeline does not disappear, make sure you create a staging app at least.

Please follow the steps below and refer to [the documentation](https://devcenter.heroku.com/articles/pipelines) and consult with the Station team if you have any further questions.

## See also

Make sure to read the Station docs to find out how to configure your repo:

- [Station docs](https://github.com/Nexmo/station/blob/master/docs/index.md)
- [Contribution Guide](https://developer.nexmo.com/contribute/overview)
- [Minimal doc product hosted on Heroku](https://minimal-doc-product.herokuapp.com/)
