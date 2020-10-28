# minimal-doc-product

## Overview

Minimal doc product is a small repo that is designed to give you an starting point so you can bootstrap your own documentation project. It provides a minimal set of configuration files and content. You could fork this repo and then add your own content, and the modify the configuration to create custom landing pages. You can also swap out logos to match your product.

> **NOTE:** Where directories must be present, but where those directories do not currently have any content, the directories are preserved by using `.gitkeep` files.

## How to use

### To simply run locally

`NOTE: Commands are to be executed on Linux, Mac, and Windows(using Powershell)`

1. Make sure you have permissions for https://rubygems.pkg.github.com/nexmo. Instructions are [here](https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-rubygems-for-use-with-github-packages)

2. Clone the repo by running the command:

```sh
$ git clone https://github.com/nexmo-community/minimal-doc-product.git
```

3. Go inside the cloned directory by command:

```sh
$ cd minimal-doc-product
```

4. Check the `Gemfile` for the correct Ruby version and select the correct version, for example:

``` sh
rbenv 2.5.8
rbenv local 2.5.8
```

> **NOTE:** This assumes you have `rbenv` installed. You can install `rbenv` on Mac with `brew install rbenv`.

6. Run `bundle install` to install your dependencies.

7. Now, you are ready to run Station:

``` sh
OAS_PATH="`pwd`/_open_api/api_specs/definitions" bundle exec nexmo-developer --docs=`pwd`
```

8. Navigate your web browser to `localhost:3000` to display the documentation landing page.

### To use as the starting point for your own product

If you want to use this repo as the starting point for your own doc product you can **fork** this repo on GitHub by clicking on the <kbd><b>Fork</b></kbd></a> button (Top-Right).

> **NOTE:** It is recommended you periodically [check for changes](https://rick.cogley.info/post/update-your-forked-repository-directly-on-github/) to the upstream project to make sure you are aware of any fixes to this repository. 

## Setting up Heroku

To build and publish your docs you will typically need to set up a Heroku pipeline. If you are not sure how to do this consult with the Station team. However, the process is summarized here, and examples are available.

A pipeline is available in Heroku for `minimal-doc-product`. You can also look at the `nexmo-developer` pipeline as another example of how to set up the pipeline.

For your repo you can create a new Heroku pipeline. A Heroku `app.json` file is included. The process is:

1. In your GitHub repo, give admin access to the Automation team NexmoDev.
2. In Heroku create a [new pipeline](https://devcenter.heroku.com/articles/pipelines).
3. For your pipeline, enable Review Apps.
4. Configure URL pattern to be `name-of-repo` plus PR number. For example: `minimal-doc-product-pr-123.herokuapp.com`.
5. Set the app config variables.
6. Submit a PR and ensure the review app is building.
7. Create a staging application for the pipeline.

> **IMPORTANT:** If you don't have a staging or production app, when the last PR is merged, and there are no review apps, **the pipeline will be automatically deleted!** To ensure your pipeline does not disappear, make sure you create a staging app at least.

## See also

Make sure you read the Station docs to find out how to configure your repo:

* [Station docs](https://github.com/Nexmo/station/blob/master/docs/index.md)
* [Contribution Guide](https://developer.nexmo.com/contribute/overview)
* [Minimal doc product hosted on Heroku](https://minimal-doc-product.herokuapp.com/)
