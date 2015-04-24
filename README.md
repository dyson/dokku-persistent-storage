DEPRECIATED
===========

Dokku docker options (a more useful dokku plugin, which will also handles persistent storage) was merged into dokku at https://github.com/progrium/dokku/commit/df8f4fb8824550518b07c87ac56aba568bd81295

There is no need to use this plugin if your running a dokku version after this. This plugin will no longer be maintained.

dokku-persistent-storage
========================

Basic persistent storage for dokku (https://github.com/progrium/dokku).

For a more useful dokku plugin, which will also handles persistent storage, check out dokku-docker-options (https://github.com/dyson/dokku-docker-options).

Requirements
------------

Development version of dokku at or after https://github.com/progrium/dokku/commit/c77cbf1d3ae07f0eafb85082ed7edcae9e836147.

Installation
------------

```bash
$ cd /var/lib/dokku/plugins
$ sudo git clone https://github.com/dyson/dokku-persistent-storage.git persistent-storage
````

Usage
-----

In your applications folder (/home/dokku/app_name) create a file called PERSISTENT_STORAGE.

Inside this file list one volume-map/volume per line to mount*. For example:

```bash
/host/path:/container/path
/another/container/path
```

The above example will result in the following arguments being passed to docker during deploy and docker run:

```bash
-v /host/path:/container/path -v /another/container/path
```

You may also include comments (lines beginning with a #) and blank lines in the PERSISTENT_STORAGE file.

Move information on docker volumes can be found here: http://docs.docker.io/en/latest/use/working_with_volumes/ .

License
-------

MIT.
