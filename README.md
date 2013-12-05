dokku-persistent-storage
========================

Basic persistent storage for dokku.

Requirements
------------

Development version of dokku (https://github.com/progrium/dokku).

Installation
------------

````
cd /var/lib/dokku/plugins
sudo git clone https://github.com/dyson/dokku-persistent-storage.git persistent-storage
````

Usage
-----

In your applications folder (/home/dokku/app_name) create a file called PERSISTENT_STORAGE.

Inside this file list one volume-map/volume per line to mount. For example:

````
/host/path:/container:path
/another/container/path
````

This will result in the following arguments being passed to docker during deploy and docker run:

````
-v /host/path:/container:path -v /another/container/path
````
