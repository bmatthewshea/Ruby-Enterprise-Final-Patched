##Ruby Enterprise Edition (REE) Final/Patched - 1.8.7-2012.02

A depo that actually has all original files in place and is patched twice:

* tcmalloc.cc - https://code.google.com/p/rubyenterpriseedition/issues/detail?id=74
* openssl - removed if/endif

Idea for this is from:

https://github.com/bacrossland/ruby_enterprise

(He also commited/pushed with .cvsignore intact. So it has missing files in repo - or this seems to be the reason)

Files that were missing from above - that are available here in this repo (using original REE source):

        source/configure
        source/ext/nkf/nkf-utf8/config.h
        source/lex.c
        source/parse.c
        source/vms/config.h
----

###To use this, clone and rename depo then create a definition file for use in ruby-build/rbenv:
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
