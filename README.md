# binfmt_misc
Kernel Support for miscellaneous (your favourite) exploits

No breakthrough here, just some trivia involving binary formats.

# binfmt_rootkit

Poor man's rootkit, leverage `binfmt_misc`'s "`C` - credentials" option to
drop a root shell if `/proc/sys/fs/binfmt_misc/register` is world-writeable.

```sh
$ git clone https://github.com/plcp/binfmt_misc
$ cd binfmt_misc
$ ./binfmt_rootkit --help
 Usage: ./binfmt_rootkit
	Gives you a root shell if /proc/sys/fs/binfmt_misc/register is writeable,
	note that it must be enforced by any other mean before your try this, for
	example by typing something like "sudo chmod +6 /*/*/f*/*/*r" while Dave
	is thinking that you are fixing his problem.
```

Cheap nobody to root is cheap. : )
