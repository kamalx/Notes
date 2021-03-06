# CentOS

Out of the box, CentOS minimal ISO has:

```
▶ cat /etc/centos-release
▶ uname -r
3.10.0-123.el7.x86_64

▶ yum update
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
...
▶ shutdown -r now
▶ uname -r
3.10.0-123.20.1.el7.x86_64

▶ hostnamectl
```

## Disable SELinux, IPv6



## How to find and do patching?

* [CVE-2014-9322](http://www.liquidweb.com/kb/information-on-cve-2014-9322-vulnerability-for-red-hat-and-centos/)
* [National Vulnerability Database (NVD) for CVE-2014-9322](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-9322)
* [RedHat CVE database for CVE-2014-9322](https://access.redhat.com/security/cve/CVE-2014-9322)
* [KB by Liquidweb](http://www.liquidweb.com/kb/)

Most vulnerabilities you can find at CVE knowledge base.

To verify if your kernel has downloaded the patch you can:

```
▶ rpm -q --changelog kernel | grep CVE-2014-9322
- [x86] traps: stop using IST for #SS (Petr Matousek) [1172812 1172813] {CVE-2014-9322}

▶ rpm -q --changelog glibc | grep CVE-2015
- Fix parsing of numeric hosts in gethostbyname_r (CVE-2015-0235, #1183535).
```

## Systemd

* [SysV Init to Systemd cheatsheet](https://fedoraproject.org/wiki/SysVinit_to_Systemd_Cheatsheet)
* [Socket Activation](http://0pointer.de/blog/projects/socket-activation.html)
* [Getting started with systemd](https://coreos.com/docs/launching-containers/launching/getting-started-with-systemd/)

```
▶ systemctl list-unit-files

// Query the systemd journal
▶ sudo journalctl
```

## Firewall

```
// Open port 5000 to the public
▶ firewall-cmd --zone=public --add-port=5000/tcp
▶ firewall-cmd --zone=public --add-port=5000/tcp --permanent
```

## Installing Docker

Better to use yum even if it is of lower version.

```
▶ yum info docker
▶ yum install docker
▶ systemctl start docker
▶ systemctl enable docker
```