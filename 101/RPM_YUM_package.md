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

