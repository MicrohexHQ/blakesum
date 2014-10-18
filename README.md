BLAKESUM
========

Utility to calculate BLAKE-224, -256 checksums.


Installation
------------

From source, if you have Go installed:

	$ go get github.com/BlueDragon747/blakesum


Usage
-----

	blakesum [-a=224|256] [filename1] [filename2] ...

By default calculates BLAKE-256 sum. Pass option "-a=xxx" before filenames to
calculate BLAKE-xxx, where xxx is 224 or 256.  If no filenames
specified, reads from stdin.


Examples
--------

	$ echo -n "Hello world" | blakesum
	08d6da79df4e9def59c0470f44ed659cef9921a7ad4bc73ff5b18182ae623470

	$ echo -n "Hello world" | blakesum -a=224
	3b7d637c22057241c3143b2698c390a6c395d97d1a0f0dd914ba468a

	$ blakesum /bin/sh /etc/bashrc
	BLAKE-256 (/bin/sh) = 942a4171ba7ff05161f3f5c05008dd78b10a66c3fa98b098a2e6a3ffd3f25c24
	BLAKE-256 (/etc/bashrc) = 3e3260064cd430eef4d7b41fb9c65c1e843600e49a0ec6e0560253f6c45d091b

