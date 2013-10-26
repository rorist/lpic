102.4 Use Debian package management
-----------------------------------

Summary
-------

- Install, upgrade and uninstall Debian binary packages.
- Find packages containing specific files or libraries which may or may not be installed.
- Obtain package information like version, content, dependencies, package integrity and installation status (whether or not the package is installed).

Install, upgrade and uninstall Debian binary packages
-----------------------------------------------------

### Repository ###

<pre><code>/etc/apt/sources.list           # Repository

deb http://archive.ubuntu.com/ubuntu precise universe
deb-src http://archive.ubuntu.com/ubuntu precise universe

software-properties-gtk    # GUI for Repository
</code></pre>

**deb** Binary packages.  
**deb-src** Source packages.  
**precise** Distribution name.  
**folder**  Component name or folder name.  


### Install, remove, purge a package ###
<pre><code>
apt-get update                  # Updates the list of available packages
/var/lib/apt/lists/             # List of available packages

apt-get upgrade                 # Install the newest versions of all packages currently installed on the system

apt-get install vim-runtime     # Install package. Content vimtutor
apt-get remove  vim-runtime     # Remove files of the package
apt-get purge   vim-runtime     # Delete files and configuration files

</code></pre>

### Graphic interfaces ###
<pre>
update-manager             # update manager  
software-properties-gtk    # Software source, repository  

synaptic                   # Packages manager  
aptitude                   # Packages manager  
<pre>
