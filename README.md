#CHX

This is the best way to make and execute scripting files.

If the script is non existant, it will create it, attempting to do so smartly. Otherwise it will make it executable and run it.

Examples:

	$ ls -A | awk '{ print $1, $9 }'
	-rw-r--r-- fileOne
	$ chx newFile.pl     # then exit $EDITOR
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
* awk - `.awk`.
* perl - `.pl` or `.pm`.
* perl6 - `.p6` or `.p6m`.
* python - `.py`.
* zsh - `.zsh`.
* bash - anything else.
