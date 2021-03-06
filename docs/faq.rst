***
FAQ
***

I want to start new project with Brunch. What's the workflow?
-------------------------------------------------------------

* Create new project (usually from brunch-with-chaplin skeleton) ``brunch new project && cd project`.
* Create HTML mockups in ``app/assets`` directory (``login.html``, ``user.html`` etc.) & corresponding styles.
* Watch application files with ``brunch watch --server`` and see the results in browser on ``localhost:3000``. Auto-debug styles in browser, preferably with LiveReload.
* When all mockups are done, create app classes for them with ``brunch generate``. E.g. ``brunch generate scaffold user``.
* Debug your code in browser via ``console.log`` or ``debugger`` statements.

I don't like CoffeeScript. Does brunch work for pure js projects?
-----------------------------------------------------------------

Yep! Execute ``brunch new project_name --skeleton git://github.com/brunch/simple-js-skeleton.git`` and you'll create a javascript project. Customize it to your needs.

How do I change app language?
-----------------------------

For example, you want to change default `Handlebars` templates to `eco`.

* Remove ``"handlebars-brunch": "version"`` line from ``package.json``.
* Add ``"eco-brunch": "version"`` there
* Change config.files.templates.defaultExtension to ``eco`` in ``config.coffee``.

What version of plugin do I need to use? There are eco-brunch 1.0.1, 1.1.0 etc.
-------------------------------------------------------------------------------

Brunch x.y.z releases are compatible with plugins (in this case `eco-brunch`) x.(<= y).*. It means that:

You can use:
    * brunch 1.1.0 with plugin 1.0.0.
    * brunch 1.1.0 with plugin 1.1.9.
    * brunch 1.9.14 with plugin 1.5.6.

You can't use:
    * brunch 1.1.0 with plugin 1.2.0.
    * brunch 1.1.0 with plugin 2.0.0.
    * brunch 2.0.0 with plugin 1.2.0.

Why do you use these languages in default skeletons?
----------------------------------------------------

* `CoffeeScript` is used because it plays nice with object-oriented Backbone.js nature.
* `Stylus` is used because a) it has customizable syntax (you can use or drop braces / semicolons / `:`s), unlike less / sass; b) its mixins are transparent. If you're writing ``border-radius`` in stylus with ``nib``, it's automatically expanded to all vendor prefixes. No need to use `LESS` / `SCSS` syntax. Example: https://gist.github.com/2005644.
* `Handlebars` templates are used because they are logic-less / compatible with Mustache (that has implementations in many languages) and have nice helpers system. If you're a fan of clear syntax, you might like `Jade` instead, which is much clearer than `HAML`.
