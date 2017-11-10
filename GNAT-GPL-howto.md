How-to install GNAT GPL
-----------------------

- Go to http://adacore.com/download and download the package for your OS

- Extract it (on linux):

~~~sh
tar xvf <archive_name>.tar.gz
~~~

- Create a GNAT.sh file in a place practical for you, with contents

~~~sh
export PATH=<path to extracted archive dir>/bin:$PATH
~~~

- To use GNAT GPL, just source your sh file

~~~sh
source /path/to/GNAT.sh
~~~

- You can now run

~~~sh
$ gnatls --version
GNATLS GPL 2017 (20170515-63)
Copyright (C) 1992-2017, Free Software Foundation, Inc.
This is free software; see the source for copying conditions.
There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
~~~
