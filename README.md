# minimal-doc-product

TEST ONLY

An easy way to bootstrap your documentation project.

This provides a minimal documentation set.

Note, where directories must be present, but where those directories do not currently have any content, the directories are preserved by using `.gitkeep` files.

## How to use

1. Make sure you have permissions for https://rubygems.pkg.github.com/nexmo. Instructions are [here](https://docs.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-rubygems-for-use-with-github-packages)
2. Clone this repo and change into cloned directory.
3. Run correct version of Ruby:

``` sh
rbenv 2.5.8
rbenv local 2.5.8
```

4. Run Station:

``` sh
OAS_PATH="`pwd`/_open_api/api_specs/definitions" bundle exec nexmo-developer --docs=`pwd`
```

5. Navigate your web browser to `localhost:3000` to display the documentation landing page.

## Setting up Heroku

A pipeline is avialble in Heroku for `minimal-doc-product`.

For your repo you'll need to create a new Heroku pipeline. A Heroku `app.json` file is included. The process is:

1. In your GitHub repo, give admin access to the Automation team NexmoDev.
2. In Heroku create a [new pipeline](https://devcenter.heroku.com/articles/pipelines).
3. For your pipeline, enable Review Apps.
4. Configure URL patterm to be `name-of-repo` plus PR number. For example: `minimal-doc-product-pr-123.herokuapp.com`.
5. Set the app config variables.

## See also

* [Contribution Guide](https://developer.nexmo.com/contribute/overview)
* [Station docs](https://github.com/Nexmo/station/blob/master/docs/index.md)
