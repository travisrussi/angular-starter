angular-starter
===============

Angular starter project with ngBoilerplate, angular-ui Bootstrap

##Adding a New Controller to ngBoilerplate
Adding a new **controller** is pretty straight-forward.  I usually just clone an existing **src/app** folder to get the new **controller** setup.

This example creates a new **contact** controller. 

Copy and paste the **src/app/home** folder into a new **src/app/contact** folder:

    $ mkdir src/app/contact
    $ cp -r src/app/home/. src/app/contact

Rename all the **home** files to **contact** files:

    $ cd src/app/home
    $ ls home.* | awk '{print("mv "$1" "$1)}' | sed 's/home/contact/2' | /bin/sh
    
Replace all instances of **home** with **contact** in the files:

    $ sed -i '' 's/home/contact/g' *.*
    $ sed -i '' 's/Home/Contact/g' *.*
    
In the **app.js** file, add a reference to **ngBoilerplate.contact** in the module definition on line 6:

    angular.module( 'ngBoilerplate', [
      'templates-app',
      'templates-common',
      'ngBoilerplate.home',
      'ngBoilerplate.about',
      'ngBoilerplate.contact',
      'ui.state',
      'ui.route'
    ])
    
To see the change, edit the **index.html** file's header to link to the new **contact** page we just created.  On line 58, add this:

    <li ui-route="/contact" ng-class="{active:$uiRoute}">
        <a href="#/contact">
            <i class="icon-book"></i>
            Contact
        </a>
    </li>

Lastly, edit the **contact.tpl.html** file, so it's different than the cloned **home** page:

     <h1>My New Contact Page Rocks!</h1>

If you add a new folder to the **src/app** folder, the **grunt watch** won't usually pick that up.  You'll need to restart the **grunt watch** command.

##Original Build Instructions
These are just my notes on how I created the initial starter package (for future reference).

###Angular ngBoilerplate - https://github.com/joshdmiller/ng-boilerplate
ngBoilerplate is the baseline app that gets cloned

    $ git clone git://github.com/joshdmiller/ng-boilerplate angular-starter
    $ cd angular-starter
    $ sudo npm -g install grunt-cli karma bower
    $ sudo npm install
    $ export PATH=/usr/local/share/npm/bin:$PATH
    $ bower install
    $ grunt build

The ngBoilerplate bower configuration installs these packages:
 
* angular-bootstrap#0.3.0
* angular#1.0.7
* angular-mocks#1.0.7
* angular-ui-router#0.0.1
* angular-ui-utils#0.0.4
* bootstrap#2.3.2
* jquery#1.8.3

Launch the baseline application:

    $ open ./build/index.html

###Using LiveReload for real-time rebuilding and refreshing of HTML page

To enable LiveReload, install the Chrome extension.  Make sure to **Allow access to file URLs** in the extention's settings if you are running the HTML file from a local **file://** path.

    https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei

Then run **grunt** using the watch command:

    $ grunt watch
    
If running **grunt watch** throws this error, find and kill any **node** processes:

    Fatal error: Port 35729 is already in use by another process.

Make a change to the HTML and watch the page auto-reload in the browser:

    $ open -a TextMate src/.




