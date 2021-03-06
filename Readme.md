
## Intro

[![Build Status](https://travis-ci.org/drwetter/testssl.sh.svg?branch=master)](https://travis-ci.org/drwetter/testssl.sh)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/drwetter/testssl.sh?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

`testssl.sh` is a free command line tool which checks a server's service on
any port for the support of TLS/SSL ciphers, protocols as well as some
cryptographic flaws.

### Key features

* Clear output: you can tell easily whether anything is good or bad.
* Machine readable output.
* No installation needed: Linux, OSX/Darwin, FreeBSD, NetBSD, MSYS2/Cygwin,
  WSL work out of the box. Only OpenBSD needs bash. No need to install
  or to configure something.  No gems, CPAN, pip or the like.
* A Dockerfile is provided, there's also an offical container @ dockerhub.
* Flexibility: You can test any SSL/TLS enabled and STARTTLS service, not
  only web servers at port 443.
* Toolbox: Several command line options help you to run *your* test and
  configure *your* output.
* Reliability: features are tested thoroughly.
* Privacy: It's only you who sees the result, not a third party.
* Freedom: It's 100% open source. You can look at the code, see what's going on.
* The development is open (github) and participation is welcome.

### License

This software is free. You can use it under the terms of GPLv2, see LICENSE.
In addition starting from version 3.0rc1 if you're offering a scanner based on testssl.sh
as a public and / or paid service in the internet you need to mention to your audience that you're using
this program and where to get this program from.

### Compatibility

testssl.sh is working on every Linux/BSD distribution out of the box. Latest by 2.9dev
most of the limitations of disabled features from the openssl client are gone
due to bash-socket-based checks. As a result you can also use e.g. LibreSSL or OpenSSL
1.1.1 . testssl.sh also works on other unixoid system out of the box, supposed they have
`/bin/bash` >= version 3.2 and standard tools like sed and awk installed. An implicit
(silent) check for binaries is done when you start testssl.sh . System V needs probably
to have GNU grep installed. MacOS X and Windows (using MSYS2, Cygwin or WSL) work too.

Update notification here or @ [twitter](https://twitter.com/drwetter).

### Installation

You can download testssl.sh by cloning this git repository:

    git clone --depth 1 https://github.com/drwetter/testssl.sh.git

Or help yourself downloading the ZIP archive [https://github.com/drwetter/testssl.sh/archive/3.0.zip](https://github.com/drwetter/testssl.sh/archive/3.0.zip).
``testssl.sh --help`` will give you some help upfront. More help: see doc directory with
man pages. Older sample runs are at [https://testssl.sh/](https://testssl.sh/).

#### Running a docker container from dockerhub

     docker run -ti drwetter/testssl.sh <your_cmd_line>

### Status

We're currently in the late release candidate phase. That means you can and should use it for production
and let us know if you encounter any additional bugs. Features implemented in 3.0 are listed in the [Changelog](https://github.com/drwetter/testssl.sh/CHANGELOG.md).

Support for 2.9.5 has been dropped.


### Documentation

* It is for reading. Please do so :-) at least before asking questions.
* There's a man page in groff, html and markdown format in `~/doc/`.
* [https://testssl.sh/](https://testssl.sh/) will help to get you started.
* Will Hunt provides a longer, good [description](https://www.4armed.com/blog/doing-your-own-ssl-tls-testing/) for the version 2.8, including useful background info.


### Contributions

Contributions, feedback,  bug reports are welcome! For contributions please
note: One patch per feature -- bug fix/improvement. Please test your
changes thoroughly as reliability is important for this project.

There's a [coding guideline](https://github.com/drwetter/testssl.sh/wiki/Coding-Style).

### Bug reports

Please file bugs in the issue tracker @ github. Do not forget to provide detailed information,
see template. Details @ https://github.com/drwetter/testssl.sh/wiki/Bug-reporting. Nobody can read your
thoughts -- yet. And only agencies your screen ;-)

You can also debug yourself, see [here](https://github.com/drwetter/testssl.sh/wiki/Findings-and-HowTo-Fix-them).

----

### External/related projects

Please address questions not specifically to the code of testssl.sh to the respective projects below.

#### Cool web frontend
* https://github.com/TKCERT/testssl.sh-webfrontend

#### Mass scanner w parallel scans and elastic searching the results
* https://github.com/TKCERT/testssl.sh-masscan

#### Another ready-to-go docker image is at:
* https://quay.io/repository/jumanjiman/testssl

#### Privacy checker using testssl.sh
* https://privacyscore.org

#### Brew package

* see [#233](https://github.com/drwetter/testssl.sh/issues/233) and
  [https://github.com/Homebrew/homebrew](https://github.com/Homebrew/homebrew)

#### Daemon for batch execution of testssl.sh command files
* https://github.com/bitsofinfo/testssl.sh-processor

#### Daemon for batch processing of testssl.sh JSON result files for sending Slack alerts, reactive copying etc
* https://github.com/bitsofinfo/testssl.sh-alerts
