# minimal-doc-product

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

## See also

* [Contribution Guide](https://developer.nexmo.com/contribute/overview)
* [Station docs](https://github.com/Nexmo/station/blob/master/docs/index.md)
