# The `src/app/contact` Directory

## Overview

```
src/
  |- app/
  |  |- contact/
  |  |  |- contact.js
  |  |  |- contact.less
  |  |  |- contact.spec.js
  |  |  |- contact.tpl.html
```

- `contact.js` - defines the module.
- `contact.less` - module-specific styles; this file is imported into
  `src/less/main.less` manually by the developer.
- `contact.spec.js` - module unit tests.
- `contact.tpl.html` - the route template.

## `contact.js`

This boilerplate is too simple to demonstrate it, but `src/app/contact` could have
several sub-folders representing additional modules that would then be listed
as dependencies of this one.  For example, a `note` section could have the
submodules `note.create`, `note.delete`, `note.search`, etc.

Regardless, so long as dependencies are managed correctly, the build process
will automatically take take of the rest.

The dependencies block is also where component dependencies should be
specified, as shown below.

```js
angular.module( 'ngBoilerplate.contact', [
  'placeholders',
  'titleService'
])
```

Each section or module of the site can also have its own routes. AngularJS will
handle ensuring they are all available at run-time, but splitting it this way
makes each module more self-contained.

```js
.config([ '$routeProvider', function config( $routeProvider ) {
  $routeProvider.when( '/contact', {
    controller: 'ContactCtrl',
    templateUrl: 'contact/contact.tpl.html'
  });
}])
```

And of course we define a controller for our route, though in this case it does
nothing.

```js
.controller( 'ContactCtrl', [ '$scope', 'titleService', function ContactController( $scope, titleService ) {
  titleService.setTitle( 'Contact' );
}]);
```
