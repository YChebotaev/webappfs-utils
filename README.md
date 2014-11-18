webappfs
========

Utilities for [generic directory structure for web application](https://github.com/YChebotaev/webappfs)

wfs-init
--------

Create a root structure tree

```plain
wfs-init <dirname> [--gitkeep]
```

`<dirname>` - "mount" point of generated structure (will be `.` if omitted)

`--gitkeep` - create `.gitkeep` file inside each folder

wfs-init-app
-----------

Create directory structure for app.

**Must run inside existent structure root**

```plain
wfs-init-app <appname> [<environment>] [--gitkeep]
```

`<appname>` - name of application

`<environment>` - an running environment for an app. E.g. `stage`, `production` etc. (will be `local` if omitted)

`--gitkeep` - create `.gitkeep` file inside each folder

###example###

```bash
wfs-init-app example --gitkeep
```

Will produce following directory tree:

```plain
/web
  /apps
    /example
      /local
        /.gitkeep
  /conf.d
    /example
      /local
        /.gitkeep
  /logs
    /example
      /local
        /.gitkeep
  /pids
    /example
      /local
        /.gitkeep
```

wfs-init-conf
------------

Create program configuration for app

**Must run inside existent structure root**

```plain
wfs-init-conf <appname> <program> [<environment>] [--gitkeep]
```

`<appname>` - name of an app

`<program>` - program that config is created for

`<environment>` - an running environment for an app. E.g. `stage`, `production` etc. (will be `local` if omitted)

`--gitkeep` - create `.gitkeep` file inside created folder

###example###

```bash
wfs-init-conf example nginx -f --gitkeep
```

Will produce following directory tree:

```plain
/web
  /conf.d
    /nginx
      /example
        /local
          /.gitkeep
```

wfs-init-log
-----------

Create program logs dir for app

```plain
wfs-init-log <appname> <program> [<environment>] [--gitkeep]
```

`<appname>` - name of an app

`<program>` - program that log is created for

`<environment>` - an running environment for an app. E.g. `stage`, `production` etc. (will be `local` if omitted)

`--gitkeep` - create `.gitkeep` file inside created folder

###example###

```bash
wfs-init-log example nginx --gitkeep
```

Will produce following directory tree:

```plain
/web
  /logs
    /nginx
      /example
        /local
          /.gitkeep
```

wfs-run
-------

Run following command in app dir

```plain
wfs-run <appname> <environment>|--all <command> [<args>]
```

`<appname>` - name of an app

`<environment>` - an running environment for an app. E.g. `stage`, `production` etc. (will be `local` if omitted and no `--all` is set)

`--all` - use `--all` instead of `<environment>` if you want to run command in all environments

`<command>` - command to run

`<args>` - args to command
