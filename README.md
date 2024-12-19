 Welcome to the Intel Curated Repo of gnutls
============================================

You can find the full, unaltered Readme.MD from the gnutls project
below.

This repo contains the source for branches of gnutls that are curated
and updated to contain all security fixes. This includes older versions that have
had security fixes backported to them.

Branches with Intel fixes (and Intel version numbers) have been created for all
supported releases. The current supported branches are:
- [3.8.7-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.7-Intel) - [EOL December 19 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/1)

- [3.8.6-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.6-Intel) - [EOL July 03 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/2)

- [3.7.11-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.7.11-Intel) - [EOL May 23 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/3)

- [3.8.5-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.5-Intel) - [EOL April 04 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/4)

- [3.8.4-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.4-Intel) - [EOL March 19 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/5)

- [3.8.3-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.3-Intel) - [EOL January 16 2026](https://github.com/Marcin-Narzynski/dellinger-03/milestone/6)

- [3.8.2-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.2-Intel) - [EOL November 15 2025](https://github.com/Marcin-Narzynski/dellinger-03/milestone/7)

- [3.7.10-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.7.10-Intel) - [EOL August 03 2025](https://github.com/Marcin-Narzynski/dellinger-03/milestone/8)

- [3.8.1-Intel](https://github.com/Marcin-Narzynski/dellinger-03.git/tree/3.8.1-Intel) - [EOL August 04 2025](https://github.com/Marcin-Narzynski/dellinger-03/milestone/9)

Compiling:

Compile, test, and install gnutls:

[string]
[string]
[string]
[string]

The following flags were set for IPAS compliance:
compiler -D_FORTIFY_SOURCE=2 -fstack-protector-strong -fPIE -fPIC -fcf-protection=full -fstack-clash-protection
linker -Wl,-z,relro,-z,now

***FAQ***

*How do I know all CVEs are fixed for supported branches?

That's a great question. We do everything with GitHub Issues. If you want to see what CVEs have been fixed for what
branches, just search on closed issues.

*How do you know you haven't broken anything with the branches where fixes have been backported?

Before commits are made to our repository, we ensure all available unit tests pass. This of course
doesn't mean something hasn't broken; just that there isn't a unit test that detects it. If you feel you are getting
an incorrect result, please file an Issue (https://github.com/Marcin-Narzynski/dellinger-03.git/issues).

*What do you do to prepare a branch for curation?

We start with the raw upstream source. Once we have that, we create a branch for our curated changes. That branch is always called "\<upstream branch or tag name\>-Intel". Once the branch is created, we make two Intel specific changes:
- Embed an Intelized version number (ex. "gnutls 3.8.7-Intel")
- Change the default release build options to create a binary compliant with IPAS compiler flag expectations

After this, any relevant CVEs are backported to the branch.

*What happens when a new CVE is published for gnutls?

The steps are simple:
- The curation team will determine which branches are affected by the new CVE
- GitHub Issues will be created for each affected branch
- When the branches are patched, the corresponding Issues will be closed with information about which commit
fixes the issue.

### How long will you be supporting these branches?

Each branch is supported for 2-years from its release date. The exceptions to this are:

1. The vendor is maintaining that product for longer than our two year support window. In that case we will support it for as long as the vendor supports their product.
2. There are no new branch releases. I.e if there latest release is further than 2-years old we will continue to support it until a new release is made.
3. The vendor is maintaining the branch for less than 2-years. In that case we will follow suit and only support it as long as they support it, despite it being less than 2 years.

To take any guesswork out of how long things will be kept up to date, Milestones (https://github.com/Marcin-Narzynski/dellinger-03.git/milestones) have been created for each individually supported branch if it goes EOL before the upstream gnutls branch. If an internal release doesn't fall into that category, it is covered by blanket milestones corresponding to upstream support.


*The version of gnutls I want support for isn't here.  Can you support it?

File a New Issue (https://github.com/Marcin-Narzynski/dellinger-03.git/issues/new/choose) and let's talk.

*Is this only source or are you also supplying binaries?

At this particular time, we are only supply source. If you want binaries, please file a New Issue (https://github.com/Marcin-Narzynski/dellinger-03.git/issues/new/choose).

*I have a question that isn't answered here.  What do I do?

Please file a New Issue: (https://github.com/Marcin-Narzynski/dellinger-03.git/issues/new/choose)!

----------------------------------------------------------------------------------------------------------


[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/330/badge)](https://bestpractices.coreinfrastructure.org/projects/330)

|Branch|CI system|Status|Test suite coverage|Fuzzer coverage|
|:----:|:-------:|-----:|:------:|:-------------:|
|Master/3.8.x|Gitlab|[![build status](https://gitlab.com/gnutls/gnutls/badges/master/pipeline.svg)](https://gitlab.com/gnutls/gnutls/commits/master)|[![coverage report](https://gitlab.com/gnutls/gnutls/badges/master/coverage.svg)](https://gnutls.gitlab.io/coverage/master)|[![Fuzzer coverage report](https://gnutls.gitlab.io/coverage/master-fuzz/badge.svg)](https://gnutls.gitlab.io/coverage/master-fuzz)|
|Master/3.8.x|Github Actions|[![build status](https://github.com/gnutls/gnutls/workflows/MacOS%20CI/badge.svg)](https://github.com/gnutls/gnutls/actions)|N/A|N/A|
|3.7.x|Gitlab|[![build status](https://gitlab.com/gnutls/gnutls/badges/gnutls_3_7_x/pipeline.svg)](https://gitlab.com/gnutls/gnutls/commits/gnutls_3_7_x)|N/A|N/A|
|3.6.x|Gitlab|[![build status](https://gitlab.com/gnutls/gnutls/badges/gnutls_3_6_x/pipeline.svg)](https://gitlab.com/gnutls/gnutls/commits/gnutls_3_6_x)|N/A|N/A|


# GnuTLS -- Information for developers

GnuTLS implements the TLS/SSL (Transport Layer Security aka Secure
Sockets Layer) protocol.  Additional information can be found at
[www.gnutls.org](https://www.gnutls.org/).

This file contains instructions for developers and advanced users that
want to build from version controlled sources. See [INSTALL.md](INSTALL.md)
for building released versions.

We require several tools to check out and build the software, including:

* [Make](https://www.gnu.org/software/make/)
* [Automake](https://www.gnu.org/software/automake/) (use 1.11.3 or later)
* [Autoconf](https://www.gnu.org/software/autoconf/)
* [Python](https://www.python.org/) (use 3.6 or later)
* [Libtool](https://www.gnu.org/software/libtool/)
* [Gettext](https://www.gnu.org/software/gettext/)
* [Texinfo](https://www.gnu.org/software/texinfo/)
* [Tar](https://www.gnu.org/software/tar/)
* [Gzip](https://www.gnu.org/software/gzip/)
* [Texlive & epsf](https://www.tug.org/texlive/) (for PDF manual)
* [GTK-DOC](https://www.gtk.org/gtk-doc/) (for API manual)
* [Git](https://git-scm.com/)
* [Perl](https://www.cpan.org/)
* [Nettle](https://www.lysator.liu.se/~nisse/nettle/)
* [p11-kit](https://p11-glue.github.io/p11-glue/p11-kit.html)
* [gperf](https://www.gnu.org/software/gperf/)
* [libtasn1](https://www.gnu.org/software/libtasn1/) (optional)
* [Libidn2](https://www.gnu.org/software/libidn/#libidn2) (optional, for internationalization of DNS, IDNA 2008)
* [Libunistring](https://www.gnu.org/software/libunistring/) (optional, for internationalization)
* [AWK](https://www.gnu.org/software/awk/) (for make dist, pmccabe2html)
* [bison](https://www.gnu.org/software/bison) (for datetime parser in certtool)
* [libunbound](https://unbound.net/) (for DANE support)
* [libabigail](https://pagure.io/libabigail/) (for abi comparison in make dist)
* [tpm2-tss](https://github.com/tpm2-software/tpm2-tss) (for TPM 2.0 support; optional)
* [tcsd](https://trousers.sourceforge.net/) (for TPM support; optional)
* [swtpm](https://github.com/stefanberger/swtpm) (for TPM test; optional)
* [tpm-tools](https://trousers.sourceforge.net/) (for TPM test; optional)
* [tpm2-tools](https://github.com/tpm2-software/tpm2-tools/) (for TPM 2.0 test; optional)
* [tpm2-tss-engine](https://github.com/tpm2-software/tpm2-tss-engine/) (for TPM 2.0 test; optional)
* [ncat](https://nmap.org/download.html) (for TPM test; optional)
* [expect](https://core.tcl.tk/expect/index) (for TPM test; optional)

The required software is typically distributed with your operating
system, and the instructions for installing them differ.  Here are
some hints:

Debian/Ubuntu:
```
apt-get install -y dash git-core autoconf libtool gettext autopoint
apt-get install -y automake python3 nettle-dev libp11-kit-dev libtspi-dev libunistring-dev
apt-get install -y libtasn1-bin libtasn1-6-dev libidn2-0-dev gawk gperf
apt-get install -y libtss2-dev libunbound-dev dns-root-data bison gtk-doc-tools
apt-get install -y texinfo texlive texlive-plain-generic texlive-extra-utils
```

__NOTE:__ Some software versions might not be available in older releases, e.g. `nettle-dev`. 
Available backport repos, APT-Pinning or source code compiling can be used to install these versions (and dependencies) from a newer release.

Fedora/RHEL:
```
yum install -y dash git autoconf libtool gettext-devel automake patch
yum install -y nettle-devel p11-kit-devel libunistring-devel
yum install -y tpm2-tss-devel trousers-devel libtasn1-devel libidn2-devel gawk gperf
yum install -y libtasn1-tools unbound-devel bison gtk-doc texinfo texlive
```

Sometimes, you may need to install more recent versions of Automake,
Nettle, and P11-kit, which you will need to build from sources. 

Dependencies that are used during make check or make dist are listed below.
Moreover, for basic interoperability testing you may want to install openssl
and mbedtls.

* [Valgrind](https://valgrind.org/) (optional)
* [Libasan](https://gcc.gnu.org//) (optional)
* [faketime](https://github.com/wolfcw/libfaketime) (preferred) or
  [datefudge](https://packages.debian.org/datefudge) (optional)
* [nodejs](https://nodejs.org/) (needed for certain test cases)
* [softhsm](https://www.opendnssec.org/softhsm/) (for testing smart card support)
* [dieharder](https://www.phy.duke.edu/~rgb/General/dieharder.php) (for testing PRNG)
* [lcov](https://linux-test-project.github.io/) (for code coverage)
* [util-linux](https://github.com/karelzak/util-linux) or just [lscpu](https://github.com/NanXiao/lscpu) (for CPU feature detection)
* [libev](http://software.schmorp.de/pkg/libev.html) (for testing)

Debian/Ubuntu:
```
apt-get install -y valgrind nodejs softhsm2 faketime lcov libssl-dev libcmocka-dev expect libev-dev
apt-get install -y dieharder openssl abigail-tools socat net-tools ppp util-linux
```

__NOTE:__ `libubsan0` and `libasan1` are required on older versions of Ubuntu <= 16.04. This packages must be manually added on these versions:

```
apt-get install -y v libubsan0 libasan1
```

Fedora/RHEL:
```
yum install -y valgrind libasan libasan-static libubsan nodejs softhsm faketime lcov openssl-devel expect libev-devel
yum install -y dieharder mbedtls-utils openssl libabigail libcmocka-devel socat util-linux
```


To download the version controlled sources:

```
$ git clone https://gitlab.com/gnutls/gnutls.git
$ cd gnutls
```

The next step is to bootstrap and ./configure:

```
$ ./bootstrap
$ ./configure
```

When built this way, some developer defaults will be enabled.  See
cfg.mk for details.

Then build the project normally, and run the test suite.

```
$ make
$ make check
```

To test the code coverage of the test suite use the following:
```
$ ./configure --enable-code-coverage
$ make && make check && make code-coverage-capture
```

Individual tests that may require additional hardware (e.g., smart cards)
are:
```
$ sh tests/suite/testpkcs11
```

# Building for windows

It is recommended to cross compile using Fedora and the following
dependencies:

```
yum install -y wine mingw32-nettle mingw32-libtasn1 mingw32-gcc
```

and build as:

```
mingw32-configure --disable-non-suiteb-curves --disable-doc --without-p11-kit
mingw32-make
mingw32-make check
```

# Continuous Integration (CI)

We utilize two continuous integration systems, the gitlab-ci and travis.
Gitlab-CI is used to test most of the Linux systems (see .gitlab-ci.yml),
and is split in two phases, build image creation and compilation/test. The
build image creation is done at the gnutls/build-images subproject and
uploads the image at the gitlab.com container registry. The compilation/test
phase is on every commit to gnutls project.

The Travis based CI, is used to test compilation on MacOSX based systems.


# Contributing

See [the contributing document](CONTRIBUTING.md).


Happy hacking!

----------------------------------------------------------------------
Copying and distribution of this file, with or without modification,
are permitted in any medium without royalty provided the copyright
notice and this notice are preserved.
