                    BitNami GitLab Stack 5.2.0-0
                  ==============================


1. OVERVIEW

The BitNami Project was created to help spread the adoption of freely
available, high quality, open source web applications. BitNami aims to make
it easier than ever to discover, download and install open source software
such as document and content management systems, wikis and blogging
software.

You can learn more about BitNami at http://bitnami.com

GitLab allows you to keep your code secure on your own server, manage
repositories, users and access permissions, communicate through issues,
line-commens, wiki pages and perform code reviw with merge requests. It is
powered by Ruby on Rails and completely free and open source (MIT license).

You can learn more about GitLab at http://gitlab.org

The BitNami GitLab Stack is an installer that greatly simplifies the
installation of GitLab and runtime dependencies. It includes ready-to-run
versions of Apache, MySQL and Ruby On Rails. GitLab Stack is distributed 
for free under the Apache 2.0 license. Please see the appendix for the specific
licenses of all open source components included.

You can learn more about BitNami Stacks at http://bitnami.com/stacks/

2. FEATURES

- Easy to Install

BitNami Stacks are built with one goal in mind: to make it as easy as
possible to install open source software. Our installers completely automate
the process of installing and configuring all of the software included in
each Stack, so you can have everything up and running in just a few clicks.

- Independent

BitNami Stacks are completely self-contained, and therefore do not interfere
with any software already installed on your system. For example, you can
upgrade your system's MySQL or Apache without fear of 'breaking' your
BitNami Stack.

- Integrated

By the time you click the 'finish' button on the installer, the whole stack
will be integrated, configured and ready to go. 

- Relocatable

BitNami Stacks can be installed in any directory. This allows you to have
multiple instances of the same stack, without them interfering with each other. 

3. COMPONENTS

BitNami GitLab Stack ships with the following software versions:

  - GitLab 5.2.0
  - Apache 2.4.4
  - ImageMagick 6.7.5
  - MySQL 5.5.30
  - Git 1.8.2
  - Ruby 1.9.3-p429
  - Rails 3.2.13
  - RubyGems 1.8.12

4. REQUIREMENTS

To install BitNami GitLab Stack you will need:

    - Intel x86 or compatible processor
    - Minimum of 256 MB RAM 
    - Minimum of 150 MB hard drive space
    - TCP/IP protocol support
    - Compatible operantig systems:
      - An x86 Linux operating system.

5. INSTALLATION

The BitNami GitLab Stack is distributed as a binary executable installer.
It can be downloaded from:

http://bitnami.com/stacks/

The downloaded file will be named something similar to:

bitnami-gitlab-5.2.0-0-linux-installer.run on Linux or
bitnami-gitlab-5.2.0-0-linux-x64-installer.run on Linux 64 bit.

On Linux, you will need to give it executable permissions:

chmod 755 bitnami-gitlab-5.2.0-0-linux.run

To begin the installation process, double-click on that file, and you will
be greeted by the 'Welcome' screen. Pressing 'Next' will take you to the
Component Selection screen, where you can select the phpMyAdmin component. This
tool intended to handle the administration of MySQL over the web.

The next screen is the Installation Folder, where you can select where BitNami 
stack will be installed. If the destination directory does not exist, it will 
be created as part of the installation. 

The next screen will prompt you for data necessary to create the initial
admin user: 

Username and password: You will use this information to log-in into the
administrative interface. The password you provide here will also be used to
protect other parts of the installation. Please see the section named
"Usernames and Passwords" later in this document.

Email address: Your email address.

The next screen will vary, depending on whether the ports needed by the
bundled Apache and MySQL are already taken. The default listening port for
Apache is 80 and for MySQL is 3006. If those ports are already in use by 
other applications, you will be prompted for alternate ports to use.

The next screen will allow you to configure the final details of your
GitLab installation:

Hostname: The hostname for your blog, such as www.example.com. This
information will be used by GitLab when creating certain links. You can
use an IP address but there were login issues using different browsers. It
is advisable to use a fully qualified domain name.

Once the information has been entered, the installation will proceed to copy
the files to the target installation directory and configure the different
components. One this process has  been completed, you will see the
'Installation Finished' page. You can choose to launch BitNami GitLab
Stack at this point. If you do so, your default web browser will open and
display the Welcome page for the BitNami GitLab Stack. 

If you received an error message during installation, please refer to
the Troubleshooting section.

The rest of this guide assumes that you installed BitNami GitLab
Stack in /home/user/gitlab-5.2.0-0 on Linux.

6. STARTING AND STOPPING BITNAMI GITLAB STACK

To start/stop/restart application on Linux you can use the included ctlscript.sh
utility, as shown below:

       ./ctlscript.sh (start|stop|restart)
       ./ctlscript.sh (start|stop|restart) mysql
       ./ctlscript.sh (start|stop|restart) redis
       ./ctlscript.sh (start|stop|restart) apache
       ./ctlscript.sh (start|stop|restart) sidekiq

  start      - start the service(s)
  stop       - stop  the service(s)
  restart    - restart or start the service(s)


That will start Apache service. Once started, you can open your
browser and access the following URL on Linux:

http://127.0.0.1:80/

If you are accessing the machine remotely, you will need to replace
127.0.0.1 with the appropriate IP address or hostname.

7. DIRECTORY STRUCTURE

The installation process will create several subfolders under the main
installation directory:

	apache2/: Apache Web server.
	ruby/: Ruby language.
	redis/: Redis server.
	mysql/: MySQL Database.
	apps/
	  gitlab/: GitLab application folder
	    conf/: GitLab Apache configuration files
	    htdocs/: GitLab application files

8. DEFAULT USERNAMES AND PASSWORDS

The GitLab administrative user and password are the ones you set at
installation time. 

MySQL admin user is called 'root', and its password is the same as the
GitLab administrative user password.

The default MySQL non-root account used to access the database is named
bitnami, and its password is also bitnami. 

9. TROUBLESHOOTING

This version of the BitNami GitLab stack is a preview version, and as
such, may contain a number of bugs and be a little bit rough around the
edges. We are working on the next release, which will contain several
improvements along with expanded documentation. In addition to the resources
provided below, we encourage you to post your questions and suggestions at:

http://answers.bitnami.com/

We also encourage you to sign up for our newsletter, which we'll use to
announce new releases and new stacks. To do so, just register at:
http://bitnami.com/newsletter.  

9.1 Installer

# Installer Payload Error 

If you get the following error while trying to run the installer from the
command line:

"Installer payload initialization failed. This is likely due to an
incomplete or corrupt downloaded file" 

The installer binary is not complete, likely because the file was
not downloaded correctly. You will need to download the file and
repeat the installation process. 

9.2 Apache

If you find any problem starting Apache, the first place you should check is
the Apache error log file:

/home/user/gitlab-5.2.0-0/apache2/logs/error.log on Linux or
/Applications/gitlab-5.2.0-0/apache2/logs/error.log.

9.3 MySQL

The following are some common problems: 

# Access denied when trying to connect to MySQL. 

If you get an Access Denied message while trying to connect to
MySQL, make sure you are using the correct username and password. 

# "Can't connect to server" message. 

Make sure that the MySQL daemon is up and running. Remember also that if
during installation you selected a different listening port for MySQL, you
may need to pass that as an extra command line option.

For help in troubleshooting MySQL errors, you may want to reference the
"Problems and Common Errors" section of the MySQL manual, which you will
find at http://dev.mysql.com/doc/


10. LICENSES

GitLab is distributed under the MIT License,
which is located at
https://github.com/gitlabhq/gitlabhq/blob/master/LICENSE

Redis is distributed under the terms of the three clause BSD license,
wich is located at 
http://redis.io/topics/license

Apache Web Server is distributed under the Apache License v2.0, which
is located at http://www.apache.org/licenses/LICENSE-2.0

MySQL is distributed under the GNU General Public License v2, which is
located at http://www.gnu.org/licenses/old-licenses/gpl-2.0.html

Ruby is released under the Ruby License and GPL, wich is located at
http://www.ruby-lang.org/en/LICENSE.txt

Rails is released under the MIT license, which is located 
http://www.opensource.org/licenses/mit-license.php

Subversion is released under Subversion License / released under the 
terms of the Apache License, which is located at
http://subversion.tigris.org/license-1.html

RubyGems is released under the Ruby License, which is located at
http://www.ruby-lang.org/en/LICENSE.txt

Rake is released under the Ruby License, which is located at
http://www.ruby-lang.org/en/LICENSE.txt

Thin Web Server is released under the Ruby License, which 
is located at http://www.ruby-lang.org/en/LICENSE.txt

ImageMagick has its own license, which is located at
https://www.imagemagick.org/subversion/ImageMagick/trunk/LICENSE

Rmagick is released under the MIT license, which is located 
http://www.opensource.org/licenses/mit-license.php

Capistrano is released under the MIT/X Consortium License, whic is
located at http://dev.rubyonrails.org/browser/tools/capistrano/MIT-LICENSE?rev=5270

OpenSSL is released under the terms of the Apache License, which is
located at http://www.openssl.org/source/license.html

Ncurses is released under the MIT license, which is located at
http://www.opensource.org/licenses/mit-license.php

Readline is released under the GPL license, which is located at
http://www.gnu.org/copyleft/gpl.html

Zlib is released under the zlib License (a free software license/compatible 
with GPL), which is located at http://www.gzip.org/zlib/zlib_license.html

Libiconv is released under the LGPL license, which is located at
http://www.gnu.org/licenses/lgpl.html

Expat is released under the MIT license, which is located at
http://www.opensource.org/licenses/mit-license.php

Neon is released under the GNU General Public License, which is located at
http://www.gnu.org/copyleft/gpl.html

RedCloth is released under the BSD License, which is located at
http://www.opensource.org/licenses/bsd-license.php

ImageMagick has its own license, which is located at
https://www.imagemagick.org/subversion/ImageMagick/trunk/LICENSE

Rmagick is released under the MIT license, which is located 
http://www.opensource.org/licenses/mit-license.php

Freetype is released under The Freetype Project License, that is located at
http://freetype.sourceforge.net/FTL.TXT
