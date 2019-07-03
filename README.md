FileScout
=========

FileScout is a program that act as a FIM (File Integrity Monitor) for any Unix server
(AIX, HP-UX, Solaris, Linux).  It will record any changes to files in the built-in log
file filescout.log.

```

Obtaining FileScout
===================

You can download FileScout either in whole or just the single script
on [GitHub](https://github.com/RocklandLabs/FileScout/).
You can also [browse, download, or clone the development version on GitHub](https://github.com/RocklandLabs/FileScout/).

Installation
============

To install FileScout, simple take the file tidyshell and put it
in /usr/local/bin and make it executable.

```
  $ mkdir /usr/local/fim
  $ cp filescout filescout.conf /usr/local/fim
  $ chmod +x /usr/local/fim/filescout
```

Usage
=====

Running FileScout by itself will show the options:

```
  $ cd /usr/local/fim
  $ ./filescout
  ./filescout Version 1.1
  OS is linux
  Loading database file...
  Starting scan...
  File /etc/passwd size was 1166 and is now 1332
  File /etc/passwd mtime was 1504375303 and is now 1519866756
  ... scan complete.
  Saving database file...
  Found 2 changes to file(s)
  Done
```

# Contributions

Contributions are welcome.  Please post bug reports and feature
requests on the
[issue tracker](https://github.com/logological/gpp/issues).  Feel free
to fork the project and send
[pull requests](https://help.github.com/articles/using-pull-requests/)
for integration into the main distribution.
