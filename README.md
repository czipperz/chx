#CHX

This is the best way to make programming boilerplate.

There are two modes, which are automatically detected: "scripting" and "programming". They are detailed below.

##Scripting

This is the best way to make and execute scripting files.

If the script is non existant, it will create it, attempting to do so smartly, then will open it in `$EDITOR`.

If the script does exist, it will make it executable and run it.

Examples:

	$ ls -A | awk '{ print $1, $9 }'
	-rw-r--r-- fileOne
	$ chx newFile.pl     # then immediately exit $EDITOR
	$ echo 'print "hi"' >> newFile.pl
	$ chx newFile.pl
	hi
	$ cat fileOne
	echo 'asdf'
	$ ./fileOne
	zsh: permission denied: ./fileOne
	$ chx fileOne
	asdf
	$ ./fileOne
	asdf

Supported file extensions:
* `.awk` - `#!/usr/bin/awk`
* `.pl` or `.pm` - `#!/usr/bin/perl`
* `.p6` or `.p6m` - `#!/usr/bin/perl6`
* `.py` - `#!/usr/bin/env python`
* `.zsh` - `#!/usr/bin/zsh`
* anything else - `#!/usr/bin/bash`


##Programming

This is the best way to create programming boiler plate and to compile it later.

If the file is non existant, it will attempt to create some boiler plate code, then will open it in your editor.

If the file does exist, it will be compiled.

Examples:

    $ chx header.h     # then immediately exit $EDITOR
    $ cat header.h
	#ifndef HEADER_H
	#define HEADER_H

    #endif
    $ chx java.java    # then immediately exit $EDITOR
	$ cat java.java
	public class java {
        
    }
    $ chx java.java
	$ ls
	header.h java.java java.class

Supported compile time file extensions:
* `.c` - `gcc -c $filename`
* `.cpp` - `g++ -c $filename`
* `.hs` - `ghc -c $filename`
* `.java` - `javac $filename`
* `.ml` or `mli` - `ocaml $filename`

Supported boiler plate extensions:
* `.java` - generates a class with the same name
* `.h` or `.hpp` - generates a `#ifndef` tree and formats the `#define` name correctly
