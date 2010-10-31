vcsdo -- Uniform commands for git, svn, hg repositories
=======================================================

vcs are a nice invention but unfortunately even the most trivial tasks 
are achieved in different ways depending on which vcs you use. This ruby 
script tries to facilitate, e.g., updating local copies of different 
vcs.

vcsdo does not aim at being a grand unified ui. It supports only simple 
tasks.


Configuration
-------------

Configuration is done via yaml files:

* Linux: ~/.vcsdo.yml, /etc/vcsdo.yml
* Windows: %WINDIR%/vcsdo.yml, %USERPROFILE%/vcsdo.yml

In configuration files, users can define aliases for the -e or -d 
command-line option. Such a yaml file could look like this:

    ---
    aliases:
        bundle: ~/.vim/bundle
        repos: ~/src/repos


Examples
--------

Update the current directory:

    vcsdo update

Update all directories below a common root directory:

    vcsdo --each ..../myLocalCopies update

Use an alias:

    vcsdo --each @repos update

The first remaining argument can also be a VCS type. This is useful for 
certain commands so you can use aliases. E.g., create a local copy of a 
git repository in the @repos directory:

    vcsdo -d @repos git clone git://github.com/foo/bar


See "vcsdo --help" for a list of supported commands. Some commands are 
not supported for certain vcs types.

Run "vcsdo -n ..." to see which commands would be issued.


Dependency
----------
* ruby 1.8

