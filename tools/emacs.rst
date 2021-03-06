######
Emacs
######

Shortcuts
==========

* https://github.com/balle/emacs/blob/master/emacs.org

SSH
====

* SSH over multiple hops http://www.gnu.org/s/tramp/#Multi_002dhops

Remote editing
==============

* Use tramp with C-xf

.. code-block:: bash

  ssh:user@host:file

* This script will ssh back to your machine and open the file you specified on the remote host
* Borrowed from https://gist.github.com/850795

.. code-block:: bash

  #!/bin/sh
  #
  # Use this script as your EDITOR to allow editing remote files with emacsclient.
  # Works by connecting to the Emacs machine with SSH and using a suitable tramp prefix.

  # How to reach this machine from the one that's running Emacs
  ME=user@remote-host

  # How to reach the machine that's running Emacs from this machine
  THEY=user@host-running-emacs

  if [ "${1#/}" != "$1" ]; then
    # absolute path
    exec ssh $THEY "emacsclient /$ME:$1"
  else
    # relative path
    PWD=$(pwd)
    exec ssh $THEY "emacsclient /$ME:$PWD/$1"
  fi


Share a buffer over http
========================

* Install the impatient-mode package.
* Call M-x httpd-start.
* Configure the firewall to allow incoming connections.
* Put the selected buffer into impatient-mode.
* Share the link with my IP address (form: http://my.ip.ad.dress:8080/imp/)
* Copied from http://sachachua.com/blog/2015/02/emacs-peer-peer-coaching-easier-use-impatient-mode-share-buffer/


How to Write a Emacs Major Mode for Syntax Coloring
===================================================

* http://ergoemacs.org/emacs/elisp_syntax_coloring.html


Extensions
===========

* https://github.com/balle/emacs/
* http://gabrielelanaro.github.com/emacs-for-python/
* https://github.com/pdee/pdee

Useful links
============

* http://emacswiki.org/
* http://stackoverflow.com/questions/tagged/emacs
