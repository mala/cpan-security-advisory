# CPAN Security Advisory Database (CPANSA)

This is a database of the security advisories for the Perl modules uploaded to CPAN.

This is a hand-picked database. If you want to be automatically notified when one of your dependencies has a security
issue, check out <https://kritika.io>.

## Sources

- metacpan.org - modules Changes files with security fixes
- CVE databases
    - https://nvd.nist.gov/feeds/xml/cve/misc/nvd-rss.xml
- OS distributions security advisory feeds:
    - Debian https://www.debian.org/security/dsa
    - FreeBSD http://vuxml.freebsd.org/freebsd/rss.xml
    - Gentoo https://security.gentoo.org/glsa/feed.rss
    - Ubuntu https://usn.ubuntu.com/rss.xml

## Command line checks

For command line checks take a look at [CPAN-Audit](https://metacpan.org/release/CPAN-Audit) package.

```
$ cpan-audit module Catalyst '>7.0'
```

## Database format

Id format: `CPANSA-<dist-name>-<year>-<sequence>`

Database is in YAML format with a simple structure:

```
- id: CPANSA-Mojolicious-2008-01
  distribution: Mojolicious
  reported: 2011-04-05
  severity: critical
  description: >
    Directory traversal vulnerability in Path.pm in Mojolicious before 1.16 allows remote attackers to read arbitrary
    files via a %2f..%2f (encoded slash dot dot slash) in a URI.
  cves:
    - CVE-2011-1589
  references:
    - https://github.com/mojolicious/mojo/commit/b09854988c5b5b6a2ba53cc8661c4b2677da3818
    - https://www.cvedetails.com/cve/CVE-2011-1589/
  affected_versions: "< 1.16"
  fixed_versions: ">= 1.16"
```

## Maintainer

Viacheslav Tykhanovskyi (github.com/vti)

## Credits

Takumi Akiyama (github.com/akiym)

## Contribution

If you know of a security vulnerability that is not present in our database, feel free to contribute with a Pull
Request. Let's make it as complete as possible!
