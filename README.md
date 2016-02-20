The Emacsmirror
===============

The Emacsmirror collects [Emacs][emacs] Lisp packages and distributes
them in form of [Git][git] repositories -- one per package.

Packages are mirrored from Git repositories at [Github][github] and
elsewhere, from Mercurial repositories, the [Emacswiki][wiki], and
plain text files.  Regardless of what upstream uses, on the
Emacsmirror each package is available as a Git repository.

Not all packages are mirrored but with it's about 3400 packages the
Emacsmirror is by far the largest and also most up-to-date collection
available.  Packages are updated several times per week.  Instead of
keeping them around forever obsolete and/or abandoned packages are
moved to the [Emacsattic][attic], where they are no longer updated.

***
<p align="center">
  <b>
    Please consider supporting my work on the Emacsmirror
	and related tools by making a donation.
  </b>
  </br></br>
  <a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=D8BWBG6QNRHDE">
    <img alt="Donate" src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif">
  </a>
</p>
***

The super-repository and the database
=====================================

All packages in the Emacsmirror and the Emacsattic are tracked as
submodules of one [super-repository][epkgs].  The same respository
also contains a SQLite database, which contains information about all
known packages (including built-in packages and packages in the
attic).

To get your hands on this information, clone the repository.

```shell
git clone git@github.com:emacsmirror/epkgs.git ~/.emacs.d/epkgs
```

If you only want to access the database using `epkg.el` or assimilate
packages using `borg.el`, then you have to do nothing else.  If you
want to use the submodules, then you obviously also have to clone
them.

```shell
TODO
```

`epkg.el` browse the database
=============================

`epkg` is a small package for browsing the Emacsmirror's database.  It
presents information in a manner similar to `package.el`, but it is
not a package manager.

`borg.el` assimilate Emacs packages as submodules
=================================================

TODO This will be released in a few days.

`emacs.g` bootstrap your Emacs configuration
============================================

TODO This will be released in a few days.

Statistics and issues
=====================

The Emacsmirror and Melpa
=========================

The Emacsmirror does not compete with Melpa.  The two projects have
different goals but there is room for collaboration.  While I do not
personally use `package.el` (I use `borg.el` mentioned above), I am
glad it exists because it makes life as maintainer of a popular Emacs
package much easier.

Even though I don't use it myself, I have contributed a lot to Melpa,
only three people, including @milkypostman and @purcell themselves
have contributed more.  I occationally compare the information in the
Epkg and Melpa databases (see previous section), and then fix which
ever got it wrong.

Melpa does not actually use a SQLite database, but I have implemented
[`melpa-db.el`][melpa-db] which builds such a database from

Adding new packages
===================

Back when I first created the Emacsmirror I actively searched for
packages.  Later when most new packages were hosted on Github, I
mirrored all newly created Elisp repositories for new packages.

Nowadays I depend on Melpa to learn about new packages.  Once a
package has been added to Melpa it usually appears on the mirror a few
days later.  So if you want to add a new package to the Emacsmirror,
then instead add it to Melpa.

Melpa features packages, while the Emacsmirror mirrores repositories.
When a repository contains several packages which can be installed
independently, then all but one of these packages are "missing" from
Emacsmirror.

Also the Emacsmirror doesn't mirror any themes, so another ~160
packages are missing.  And it no longer supports importing from bzr,
cvs, darcs, fossil, and svn repositories.  Supporting these additional
version control systems is not worth the effort, considering that only
about twenty packages remain which use a vcs other than git or hg.

[here]:   https://github.com/emacsmirror/p
[epkgs]:  https://github.com/emacsmirror/epkgs
[attic]:  https://github.com/emacsattic

[melpa]:    https://melpa.org
[melpa-db]: https://github.com/tarsius/melpa-db

[emacs]:  http://www.gnu.org/software/emacs/emacs.html
[git]:    http://git-scm.com
[github]: https://github.com
[wiki]:   http://emacswiki.org
