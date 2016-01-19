# Ruby-Enterprise-Final-Patched
Made a depo that actually has all original files in place and is patched twice:
1: tcmalloc.cc - https://code.google.com/p/rubyenterpriseedition/issues/detail?id=74
2: openssl - removed if/endif (per:)

https://github.com/bacrossland/ruby_enterprise
(He also commited/pushed with .cvsignore intact. So it has missing files in repo - or this seems to be the reason)

Files that were missing from above - that are available here in this repo (using original REE source):



        source/configure
        source/ext/nkf/nkf-utf8/config.h
        source/lex.c
        source/parse.c
        source/vms/config.h

