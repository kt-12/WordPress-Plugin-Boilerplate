

# WordPress Plugin Boilerplate

A PSR-2 revamp of [DevinVinson/WordPress-Plugin-Boilerplate](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate) project. The next phase is to implement PSR-4 autoloading.

# Why this Project?

A few months back, I started exploring WordPress boilerplates available on GitHub and I found that most of them have implemented actions and filters in the class constructor. 

The issue with this implementation is that the instantiation of these class is dependent on functions from WordPress core. This makes it hard to create unit test cases for that class because in order to instantiate the class we need to first create the mockup of the WordPress functions used in the constructor. The only way to get around was to either have action and filter implemented else where or to create a mockup function for action and filters.
A brief explanation of this problem is given here [WordPress StackExchange: Testing hooks callback](https://wordpress.stackexchange.com/questions/164121/testing-hooks-callback)

DevinVinson/WordPress-Plugin-Boilerplate has beautifully implemented these calls to the actions and the filters using a loader mechanism implemented outside this class in a separate class. This helps in creating a class that concentrates only on the functionality part and not on how and when its functions are called. 

I definitely love this boilerplate and want to take it a bit forward. What I am trying to achieve in my project is to replicate `DevinVinson/WordPress-Plugin-Boilerplate` boilerplate, convert it to PSR-2 coding standards. Eventually, I'll be implementing PSR-4 autoloading and also will be making the structure composer friendly. This will help to create plugins that reuse the feature already available in the composer.


> **Note: Most of the content mentioned below are directly copied from `DevinVinson/WordPress-Plugin-Boilerplate` README file**

## Contents

The WordPress Plugin Boilerplate includes the following files:

* `.gitignore`. Used to exclude certain files from the repository.
* `CHANGELOG.md`. The list of changes to the core project.
* `README.md`. The file that you’re currently reading.
* A `plugin-name` directory that contains the source code - a fully executable WordPress plugin.

## Features

* The Boilerplate is based on the [Plugin API](http://codex.wordpress.org/Plugin_API), [PSR-2 Coding Standards](http://www.php-fig.org/psr/psr-2/), and [Documentation Standards](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/php/), [PSR-4 Autoloading Standards](http://www.php-fig.org/psr/psr-4/) .
* All classes, functions, and variables are documented so that you know what you need to be changed.
* The Boilerplate uses a strict file organization scheme that correspond both to the WordPress Plugin Repository structure, and that makes it easy to organize the files that compose the plugin.
* The project includes a `.pot` file as a starting point for internationalization.

## Installation

The Boilerplate can be installed directly into your plugins folder "as-is". You will want to rename it and the classes inside of it to fit your needs.

Note that this will activate the source code of the Boilerplate, but because the Boilerplate has no real functionality so no menu items, meta boxes, or custom post types will be added.


## Recommended Tools

### i18n Tools

The WordPress Plugin Boilerplate uses a variable to store the text domain used when internationalizing strings throughout the Boilerplate. To take advantage of this method, there are tools that are recommended for providing correct, translatable files:

* [Poedit](http://www.poedit.net/)
* [makepot](http://i18n.svn.wordpress.org/tools/trunk/)
* [i18n](https://github.com/grappler/i18n)

Any of the above tools should provide you with the proper tooling to internationalize the plugin.

## License

The WordPress Plugin Boilerplate is licensed under the GPL v2 or later.

> This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License, version 2, as published by the Free Software Foundation.

> This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

> You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA

A copy of the license is included in the root of the plugin’s directory. The file is named `LICENSE`.

## Important Notes

### Licensing

The WordPress Plugin Boilerplate is licensed under the GPL v2 or later; however, if you opt to use third-party code that is not compatible with v2, then you may need to switch to using code that is GPL v3 compatible.

For reference, [here's a discussion](http://make.wordpress.org/themes/2013/03/04/licensing-note-apache-and-gpl/) that covers the Apache 2.0 License used by [Bootstrap](http://twitter.github.io/bootstrap/).

### Includes

Note that if you include your own classes or third-party libraries, there are three locations in which said files may go:

* `plugin-name/includes` is where functionality shared between the admin area and the public-facing parts of the site reside
* `plugin-name/admin` is for all admin-specific functionality
* `plugin-name/frontend` is for all public-facing functionality

Note that previous versions of the Boilerplate did not include `PluginNameLoader` but this class is used to register all filters and actions with WordPress.

The example code provided shows how to register your hooks with the Loader class.

# Credits

All credits goes to [DevinVinson/WordPress-Plugin-Boilerplate](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate)

