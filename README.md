RethinkDB Playground
====================

Experimenting with RethinkDB cluster setup.


Requirements
------------

  * [Vagrant](http://downloads.vagrantup.com/) 1.5+
  * [Ansible](http://www.ansibleworks.com/docs/intro_installation.html) 1.5+
  * 1.5 GB RAM available

Installation
------------

Add the followind lines to your `/etc/hosts`:

```
# rethinkdb-playground
10.0.60.2       db1.rethinkdb.dev
10.0.60.3       db2.rethinkdb.dev
10.0.60.4       db3.rethinkdb.dev
```

Next, do this:

```bash
git clone git@github.com:laggyluke/rethinkdb-playground.git
cd rethinkdb-playground
vagrant up
```

After provisioning is done, the web UIs will be available here:

* [db1.rethinkdb.dev](http://db1.rethinkdb.dev:8080/)
* [db2.rethinkdb.dev](http://db2.rethinkdb.dev:8080/)
* [db3.rethinkdb.dev](http://db3.rethinkdb.dev:8080/)
