dokku-persistent-storage
========================

Basic persistent storage for dokku (https://github.com/progrium/dokku).

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

Move information on docker volumes can be found here: http://docs.docker.io/en/latest/use/working_with_volumes/ .

_* Lines must end with a new line character. You can verify your line endings with:_ `cat -E PERSISTENT_STORAGE`
_and new line characters will be shown as $._

License
-------

MIT.
