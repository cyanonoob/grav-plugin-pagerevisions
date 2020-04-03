# Pagerevisions Plugin
Based on [Admin Addon Revisions by David Szabo](https://github.com/david-szabo97/grav-plugin-admin-addon-revisions), updated for Grav 1.7.x (with the help of [ricardo118](https://github.com/ricardo118))

The **Pagerevisions** Plugin is an extension for [Grav CMS](http://github.com/getgrav/grav). Page revisions for Grav

## Installation

Installing the Pagerevisions plugin can be done in one of three ways: The GPM (Grav Package Manager) installation method lets you quickly install the plugin with a simple terminal command, the manual method lets you do so via a zip file, and the admin method lets you do so via the Admin Plugin.

### GPM Installation (Preferred)

To install the plugin via the [GPM](http://learn.getgrav.org/advanced/grav-gpm), through your system's terminal (also called the command line), navigate to the root of your Grav-installation, and enter:

    bin/gpm install pagerevisions

This will install the Pagerevisions plugin into your `/user/plugins`-directory within Grav. Its files can be found under `/your/site/grav/user/plugins/pagerevisions`.

### Manual Installation

To install the plugin manually, download the zip-version of this repository and unzip it under `/your/site/grav/user/plugins`. Then rename the folder to `pagerevisions`. You can find these files on [GitHub](https://github.com//grav-plugin-pagerevisions) or via [GetGrav.org](http://getgrav.org/downloads/plugins#extras).

You should now have all the plugin files under

    /your/site/grav/user/plugins/pagerevisions
	
> NOTE: This plugin is a modular component for Grav which may require other plugins to operate, please see its [blueprints.yaml-file on GitHub](https://github.com//grav-plugin-pagerevisions/blob/master/blueprints.yaml).

### Admin Plugin

If you use the Admin Plugin, you can install the plugin directly by browsing the `Plugins`-menu and clicking on the `Add` button.

## Configuration

Before configuring this plugin, you should copy the `user/plugins/pagerevisions/pagerevisions.yaml` to `user/config/plugins/pagerevisions.yaml` and only edit that copy.

Here is the default configuration and an explanation of available options:

```yaml
enabled: true
directory: .revs
limit:
  maximum: 10
  older: 1 month
ignore_files: []
```

* `directory` - revisions will be stored in this folder inside the page's folder

* `limit.maximum` - limits the number of revisions per page (use `0` to disable)

* `limit.older` - limits the number of revisions per page by checking the creation date of the revision, works with any `strtotime` compatible string. (1 month, 2 months, 1 day, 30 days, etc.)  (use `0` to disable)

* `ignore_files` - an array of regular expressions to ignore files when looking for changes between revisions

  In this example we ignore all `png` and `jpg` files in the `test` page's folder.
  ```
  /pages\/test\/(.*).png$/
  /pages\/test\/(.*).jpg$/
  ```
  If you want to ignore `png` files in all pages' folders then you can use something like this:
  ```
  /png$/
  ```

## Usage

A **Revisions** link will appear in the **Admin** navigation sidebar. By navigating to the **Revisions** you can check the differences and delete/revert a specific revision.

## To Do

- [ ] Translation support - mostly done
- [ ] Add more translations
- [ ] ???
- [ ] Non-profit


