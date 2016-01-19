##Ruby Enterprise Edition (REE) Final/Patched - 1.8.7-2012.02

A depo for the last version of REE that is also patched twice:

* tcmalloc.cc - https://code.google.com/p/rubyenterpriseedition/issues/detail?id=74
* openssl - removed if/endif

----

###Use in ruby-build/rbenv:
Clone and rename depo then create a definition file for use in ruby-build/rbenv:
```
git clone https://github.com/bmatthewshea/Ruby-Enterprise-Final-Patched.git
mv Ruby-Enterprise-Final-Patched/ ruby-enterprise-1.8.7-2012.02-custom/
tar czf ruby-enterprise-1.8.7-2012.02-custom.tar.gz ruby-enterprise-1.8.7-2012.02-custom/
```
Sample definition file 'ree-1.8.7-2012.02-custom':
```
require_gcc
install_package "ruby-enterprise-1.8.7-2012.02-custom" "file:///home/USERNAME/downloads/ruby-enterprise-1.8.7-2012.02-custom.tar.gz" ree_installer
```
Run ruby-build via rbenv as example:
```
rbenv install ./ree-1.8.7-2012.02-custom
```
if you experince segfaults try:
```
CFLAGS="-O2 -fno-tree-dce -fno-optimize-sibling-calls" rbenv install ./ree-1.8.7-2012.02-custom
```



Note: I have reproduced this install method/build. If you feel there is an error, just let me know..

----

###Reason

https://github.com/bacrossland/ruby_enterprise

I created this because after trying to use the that, I was missing files.
I needed quick way to clone source out for migration.
Files that were missing from above - that are available here in this repo (using original REE source):

        source/configure
        source/ext/nkf/nkf-utf8/config.h
        source/lex.c
        source/parse.c
        source/vms/config.h

(Seems to have commited/pushed with .cvsignore intact? or this seems to be the reason for missing files)

