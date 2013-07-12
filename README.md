angular-starter
===============

Angular starter project with ngBoilerplate, angular-ui Bootstrap


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




