TidyShell
=========

TidyShell is a program that will take any POSIX, Korn, or BASH script
and tidy (or beautify?) it up so that the spacing is consistent throughout it.
It will take an `if (expr); then` and split it into two lines.  It will do the same
for `while (expr); do`.  It will ensure the spacing is consitent with `case` and
`if-then-else` statements as well.

It can take a script like this:


```
#!/bin/sh

# Some comment.
for i in 1 2 3 4
do
    while [ $i -gt 2 ]; do
        :
    done
                    if [ $i -eq 0 ]
then
        :
    elif [ $i -eq 1 ]; then
        :
    else
        :
    fi
    case $i in
        1) : ;;
        2)
                           :
                ;;
esac
                   done

subname() {
:
}
```


And turn it into this:


```#!/bin/sh

# Some comment.
for i in 1 2 3 4
do
    while [ $i -gt 2 ]
    do
        :
    done
    if [ $i -eq 0 ]
    then
        :
    elif [ $i -eq 1 ]
    then
        :
    else
        :
    fi
    case $i in
        1) : ;;
        2)
            :
        ;;
    esac
done

subname() 
{
    :
} 
```

Obtaining TidyShell
===================

You can download TidyShell either in whole or just the single script
on [GitHub](https://github.com/RocklandLabs/TidyShell/).
You can also [browse, download, or clone the development version on GitHub](https://github.com/RocklandLabs/TidyShell/).

Installation
============

To install TidyShell, simple take the file tidyshell and put it
in /usr/local/bin and make it executable.

```
$ cp tidyshell /usr/local/bin
$ chmod +x /usr/local/bin/tidyshell
```

Usage
=====

Running TidyShell by itself will show the options:

```
$ tidyshell
tidyshell v1.6
ERROR: The input file doesn't exist
Usage:: ./tidyshell [options] -i <inputfile> -o <outputfile>
where [options] are as follows:
  -d = turn on debug mode [optional]
  -h = print out this usage screen
  -i <inputfile> = specify the name of the input file
  -n # = set the indent to be # spaces [optional, default is 4]
  -o <outputfile> = specify the name of the output file [optional]
```

To run it against a script:

```
$ tidyshell -i sample1.sh
```

To run it against a script and make the spaces 2:

```
$ tidyshell -n 2 -i sample1.sh
```

To run it against a script and send the output to another file:

```
$ tidyshell -i sample1.sh -o sample1.clean.sh
```

# Contributions

Contributions are welcome.  Please post bug reports and feature
requests on the
[issue tracker](https://github.com/logological/gpp/issues).  Feel free
to fork the project and send
[pull requests](https://help.github.com/articles/using-pull-requests/)
for integration into the main distribution.
