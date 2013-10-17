102.4 Use Debian package management
-----------------------------------

Summary
-------

- Install, upgrade and uninstall Debian binary packages.
- Find packages containing specific files or libraries which may or may not be installed.
- Obtain package information like version, content, dependencies, package integrity and installation status (whether or not the package is installed).

Install, upgrade and uninstall Debian binary packages
-----------------------------------------------------

- Install, remove, purge a package
<pre><code>
/etc/apt/sources.list           # Repository
apt-get update                  # Met à jour les listes des paquets disponible
/var/lib/apt/lists/             # List of available packages
apt-get install vim-runtime     # Content vimtutor
apt-get remove  vim-runtime
apt-get purge   vim-runtime     # Delete configuration files

</code></pre>
