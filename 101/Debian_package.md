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
/var/cache/apt/archives/        # Folder containing downloaded .deb files

apt-get install vim-runtime     # Install package. Content vimtutor
apt-get remove  vim-runtime     # Remove files of the package
apt-get purge   vim-runtime     # Delete files and configuration files

apt-get [-s, --simulate, --just-print, --dry-run, --recon, --no-act]  # Simulate install
apt-get [-s| --simulate] install   vim     # Simutate install

apt-get install [-d| --download-only] vim     # Download vim package without install
apt-get download vim             # download the given binary package into the current directory

apt-get remove --auto-remove vim # Remove vim and non necessary packages dependencies
apt-get autoremove               # Remove non necessary packages dependencies
</code></pre>

### Cache management ###

<pre><code>
/var/cache/apt/archives/        # Folder containing downloaded .deb files

apt-get clean        # Delete .deb files downloaded in folder /var/cache/apt/archives
apt-get autoclean    # Delete .deb files that can no longer be downloaded
</code></pre>


Obtain package information
--------------------------

### apt-cache

<pre><code>
apt-cache depends  vim           # vim depends on which packages (above vim)
apt-cache rdepends vim           # Packages below vim 
apt-cache search "linux loader"
apt-cache search kdebase         # search package kdebase
apt-cache dumpavail              # list of available packages
apt-cache show    vim            # Like dpkg --print-avail vim  
apt-cache showpkg vim            # list package name, dependencies, ver., ...
</code></pre>

### dpkg ###

<pre><code>

</code></pre>


Graphic interfaces
------------------

<pre><code>
update-manager             # update manager
software-properties-gtk    # Software source, repository

synaptic                   # Packages manager
aptitude                   # Packages manager
</code></pre>
