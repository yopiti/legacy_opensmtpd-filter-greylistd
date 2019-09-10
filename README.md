** OpenSMTPD has a new filter API, this filter will be replaced by a new one **

OpenSMTPD greylist support
==========================

**Still under active development**

Debian ships with `greylistd`, a simple greylist management server written in
Python. `greylistd` implements a simple protocol over a local socket that
manages the greylisting of IP addresses, HELO hostnames and RCPT addresses.
This filter **only** uses the sender's host's IP address.

How to use this
---------------

Once the packages are uploaded, you will be able to install it like this:

```
echo "deb http://repo.maurus.net/greylistd jessie main" > /etc/apt/sources.list.d/greylistd.list
apt-get update
apt-get install greylistd opensmtpd-filter-greylistd
```

In your OpenSMTPD configuration activate `filter_greylistd`:

```
filter greylistd greylistd "-s" "/var/run/greylistd/socket"
```

TODO: finish integration


Build
-----

`compile.sh` does most of the heavy lifting as long as you execute it in the
base folder and have `autoconf1.15` and `libtool` installed.

