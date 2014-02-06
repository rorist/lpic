102.5 Use RPM and YUM package management
----------------------------------------

Summary
-------

- Install, re-install, upgrade and remove packages using RPM and YUM.
- Obtain information on RPM packages such as version, status, dependencies, integrity and signatures.
- Determine what files a package provides, as well as find which package a specific file comes from.

Install, re-install, upgrade and remove packages using RPM and YUM
------------------------------------------------------------------

### RPM ###

* rpm -q package-to-search
* rpm -q -l package #list provided files
* rpm -q

### YUM repositories ###

* In /etc/yum.repos.d/
** Format of the repo url is
 http://mirror.centos.org/centos/$releasever/os/$basearch/
    where releasever=6.5
          basearch=x86_64
** Possibility to enable or not the repo
* Minimum repo definition
<pre>
[repository]
name=repository_name
baseurl=repository_url
</pre>
* Example of a repo definition
<pre>
[base]
name=CentOS-$releasever - Base
mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
</pre>
* Cached package list is in /var/yum/cache/$basearch/$releasever configured in /etc/yum.conf

### Install, remove, purge, download a package with YUM

<pre><code>
yum check-update                    # Check upgradable packages
yum update                          # Upgrade the installed packages
yum upgrade                         # Upgrade the installed packages (with obsolete packages)
yum install package-name            # Install package-name
yum remove package-name             # Remove package-name
yum --nodeps remove package-name    # Remove package-name (keep dependencies)
yum list                            # List all packages from available repositories
yum list available                  # List installable packages
yum list installed                  # List installed packages on the system
yum search package name             # Search for +package +name in the available repositores
</code></pre>

* Download without installing, use the downloadonly plugin
<pre><code>
yum install yum-downloadonly
yum update --downloadonly httpd
</pre></code>

### Cache management with YUM
<pre><code>
yum makecache                       # Grab all packages metadata for caching in available repo
yum clean                           # Clean all unecessary information in yum cache
</pre></code>

### Install, remove a package with RPM
<pre><code>
rpm -i package                      # Install a package, from local file or URI (http, ftp)
rpm -e package-name                 # Remove a package from name
rpm -qa                             # Show all installed packages
rpm -qi package-name                # Display package-name information
</code></pre>

### Package informations
<pre><code>
rpm -qa --last                      # List installed packages, most recent first
rpm -q --configfiles package-name   # List configuration files for package-name
rpm -Va --nofiles --nomd5           # Check unresolved deps
rpm -ql package-name                # Show installed files of package-name
rpm -qf filename                    # Show which package installed filename
rpm --checksig                      # Check the PGP signature of a package
</code></pre>

### Graphical interfaces

* yumex


