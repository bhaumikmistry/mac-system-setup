# **Python install on mac**

**Mac OS X**
![mac os x](http://cdn.osxdaily.com/wp-content/uploads/2018/06/install-python3-mac.jpg)

*Max OS X comes with python 2.7.10*

## *Setup*
- Xcode ```xcode-select --install```
- ```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```
- There is no ~./profile by default.
    
    Some background: when you start your Terminal.app, it loads a shell – in your case Bash. Shells can have configuration files, and .profile is one of these. They are read when the shell starts up, in a specific order. You can run man bash and read the section "Invocation" for more details.

    Now, under macOS, I would recommend to not create a .profile file, but a .bash_profile file instead. For Bash, this will make no difference in functionality. Note however that once you create a file called ~/.bash_profile, your ~/.profile will not be read anymore, and since most guides will want you to modify .bash_profile, it's better to stick to this one.

    You can simply create the file if it doesn't exist and open it in a text editor.

    ```
    touch ~./bash_profile
    open -e !$
    ```
- add following line to ~./bash_profile
    ```
    export PATH="/usr/local/opt/python/libexec/bin:$PATH"
    ```
- install python 
    ```
    brew install python
    ```

### Post installation debug info
```
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> New Formulae
cpu_features               nushell                    protobuf@3.7
==> Updated Formulae
algernon                                 nativefier
angular-cli                              node
apache-arrow                             nsd
arangodb                                 nspr
armadillo                                numpy
arpack                                   nwchem
bind                                     ocaml
bit                                      ocaml-findlib
blueutil                                 ocaml-num
caffe                                    ocamlbuild
camlp4                                   ocamlsdl
camlp5                                   octave
ceres-solver                             opa
chronograf                               openapi-generator
cimg                                     openblas
citus                                    opencv
clamav                                   opencv@2
clojure                                  opencv@3
collectd                                 packer-completion
contentful-cli                           pdfcrack
credstash                                petsc
deno                                     petsc-complex
devspace                                 platformio
dynare                                   poco
embree                                   postgis
emscripten                               postgresql
eslint                                   postgresql@10
etcd                                     postgresql@9.5
exploitdb                                postgresql@9.6
firebase-cli                             postgrest
flow                                     proteinortho
fluid-synth                              protobuf
fluxctl                                  protobuf-c
fonttools                                protobuf-swift
freeipmi                                 qrupdate
futhark                                  r
gatsby-cli                               re2c
gauge                                    rebar3
get_iplayer                              rke
getmail                                  roswell
git-annex                                rsyslog
gitlab-runner                            saxon
gitversion                               scala@2.12
glooctl                                  scalapack
gmt                                      scipy
golang-migrate                           shadowenv
goofys                                   shogun
goreleaser                               snapcraft
grakn                                    speedtest-cli
grpc                                     starship
harfbuzz                                 streamlink
helmfile                                 suite-sparse
imagemagick@6                            sundials
inlets                                   svtplay-dl
ipopt                                    swig
jenkins                                  terraform
jvgrep                                   terrahub
kotlin                                   tflint
kube-aws                                 tile38
kubernetes-service-catalog-client        tomcat@7
lablgtk                                  tomcat@8
launchdns                                tomee-webprofile
ldc                                      tor
libiodbc                                 trafficserver
libosmium                                triton
libphonenumber                           tunnel
libpq                                    ucloud
libpqxx                                  vaulted
libpulsar                                velero
libraw                                   vert.x
librsync                                 vim
linkerd                                  visp
lz4                                      vnstat
mesa                                     vulkan-headers
minio                                    wtf
minio-mc                                 wtfutil
mkvtoolnix                               xonsh
mmseqs2                                  ykman
mosh                                     zbackup
mycli                                    zsdx
n                                        zstd
nagios

==> Installing dependencies for python: gdbm, openssl, readline, sqlite and xz
==> Installing python dependency: gdbm
==> Downloading https://homebrew.bintray.com/bottles/gdbm-1.18.1.mojave.bottle.1
######################################################################## 100.0%
==> Pouring gdbm-1.18.1.mojave.bottle.1.tar.gz
🍺  /usr/local/Cellar/gdbm/1.18.1: 20 files, 586.8KB
==> Installing python dependency: openssl
==> Downloading https://homebrew.bintray.com/bottles/openssl-1.0.2s.mojave.bottl
==> Downloading from https://akamai.bintray.com/c4/c4a762d719c2be74ac686f1aafabb
######################################################################## 100.0%
==> Pouring openssl-1.0.2s.mojave.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile

For compilers to find openssl you may need to set:
  export LDFLAGS="-L/usr/local/opt/openssl/lib"
  export CPPFLAGS="-I/usr/local/opt/openssl/include"

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.2s: 1,795 files, 12.0MB
==> Installing python dependency: readline
==> Downloading https://homebrew.bintray.com/bottles/readline-8.0.0_1.mojave.bot
==> Downloading from https://akamai.bintray.com/fa/faab004773e6449dd97971311cb62
######################################################################## 100.0%
==> Pouring readline-8.0.0_1.mojave.bottle.tar.gz
==> Caveats
readline is keg-only, which means it was not symlinked into /usr/local,
because macOS provides the BSD libedit library, which shadows libreadline.
In order to prevent conflicts when programs look for libreadline we are
defaulting this GNU Readline installation to keg-only.

For compilers to find readline you may need to set:
  export LDFLAGS="-L/usr/local/opt/readline/lib"
  export CPPFLAGS="-I/usr/local/opt/readline/include"

==> Summary
🍺  /usr/local/Cellar/readline/8.0.0_1: 48 files, 1.5MB
==> Installing python dependency: sqlite
==> Downloading https://homebrew.bintray.com/bottles/sqlite-3.29.0.mojave.bottle
==> Downloading from https://akamai.bintray.com/5f/5f2f8f36a8d13733b0374ac39bdcd
######################################################################## 100.0%
==> Pouring sqlite-3.29.0.mojave.bottle.tar.gz
==> Caveats
sqlite is keg-only, which means it was not symlinked into /usr/local,
because macOS provides an older sqlite3.

If you need to have sqlite first in your PATH run:
  echo 'export PATH="/usr/local/opt/sqlite/bin:$PATH"' >> ~/.bash_profile

For compilers to find sqlite you may need to set:
  export LDFLAGS="-L/usr/local/opt/sqlite/lib"
  export CPPFLAGS="-I/usr/local/opt/sqlite/include"

==> Summary
🍺  /usr/local/Cellar/sqlite/3.29.0: 11 files, 3.9MB
==> Installing python dependency: xz
==> Downloading https://homebrew.bintray.com/bottles/xz-5.2.4.mojave.bottle.tar.
==> Downloading from https://akamai.bintray.com/01/010667293df282c8bceede3bcd369
######################################################################## 100.0%
==> Pouring xz-5.2.4.mojave.bottle.tar.gz
🍺  /usr/local/Cellar/xz/5.2.4: 92 files, 1MB
==> Installing python
==> Downloading https://homebrew.bintray.com/bottles/python-3.7.4.mojave.bottle.
==> Downloading from https://akamai.bintray.com/81/81fc6e5914a16387bd09387ce08e9
######################################################################## 100.0%
==> Pouring python-3.7.4.mojave.bottle.tar.gz
==> /usr/local/Cellar/python/3.7.4/bin/python3 -s setup.py --no-user-cfg install
==> /usr/local/Cellar/python/3.7.4/bin/python3 -s setup.py --no-user-cfg install
==> /usr/local/Cellar/python/3.7.4/bin/python3 -s setup.py --no-user-cfg install
==> Caveats
Python has been installed as
  /usr/local/bin/python3

Unversioned symlinks `python`, `python-config`, `pip` etc. pointing to
`python3`, `python3-config`, `pip3` etc., respectively, have been installed into
  /usr/local/opt/python/libexec/bin

If you need Homebrew's Python 2.7 run
  brew install python@2

You can install Python packages with
  pip3 install <package>
They will install into the site-package directory
  /usr/local/lib/python3.7/site-packages

See: https://docs.brew.sh/Homebrew-and-Python
==> Summary
🍺  /usr/local/Cellar/python/3.7.4: 3,865 files, 60MB
==> Caveats
==> openssl
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile

For compilers to find openssl you may need to set:
  export LDFLAGS="-L/usr/local/opt/openssl/lib"
  export CPPFLAGS="-I/usr/local/opt/openssl/include"

==> readline
readline is keg-only, which means it was not symlinked into /usr/local,
because macOS provides the BSD libedit library, which shadows libreadline.
In order to prevent conflicts when programs look for libreadline we are
defaulting this GNU Readline installation to keg-only.

For compilers to find readline you may need to set:
  export LDFLAGS="-L/usr/local/opt/readline/lib"
  export CPPFLAGS="-I/usr/local/opt/readline/include"

==> sqlite
sqlite is keg-only, which means it was not symlinked into /usr/local,
because macOS provides an older sqlite3.

If you need to have sqlite first in your PATH run:
  echo 'export PATH="/usr/local/opt/sqlite/bin:$PATH"' >> ~/.bash_profile

For compilers to find sqlite you may need to set:
  export LDFLAGS="-L/usr/local/opt/sqlite/lib"
  export CPPFLAGS="-I/usr/local/opt/sqlite/include"

==> python
Python has been installed as
  /usr/local/bin/python3

Unversioned symlinks `python`, `python-config`, `pip` etc. pointing to
`python3`, `python3-config`, `pip3` etc., respectively, have been installed into
  /usr/local/opt/python/libexec/bin

If you need Homebrew's Python 2.7 run
  brew install python@2

You can install Python packages with
  pip3 install <package>
They will install into the site-package directory
  /usr/local/lib/python3.7/site-packages

See: https://docs.brew.sh/Homebrew-and-Python
```