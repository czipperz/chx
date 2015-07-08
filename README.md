#CHX

This is the best way to make and execute scripting files.

If the script is non existant, it will create it, attempting to do so smartly. Otherwise it will make it executable and run it.

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
