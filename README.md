# Monitoring Fritz!Box With MRTG

## upnp2mrtg
upnp2mrtg is a add-on for the
[MRTG (Multi Router Traffic Grapher)](http://oss.oetiker.ch/mrtg/).
upnp2mrtg is a command line tool written in shell to gather statistics from an
upnp enabled FritzBox DSL router.

## Features

- WAN interface monitoring
- LAN interface monitoring, if Fritz!Box isn't the router (see -P option)
- uses UPNP protocoll
- very little requirements
- configurable
- no Fritz!Box modifications required

## Fritz!Box Devices
| Modell    | Status    | Remark |
|-----------|-----------|--------|
| 3030      | ok        |	 |
| 3170      | ok        |	 |
| 5050      | ok        |	 |
| 5113      | ok        |	 |
| 7050      | ok        |	 |
| 7141      | ok        |	 |
| 7170      | ok        |	 |
| 7270      | ok        |	 |
| 7490      | ok        | needs fix |

If you have a running upnp2mrtg installation not listed here, please drop me a
note! Thanks!

## Contact
If you have problems, questions, ideas or suggestions, please contact me:
(mailto:upnp2mrtg@ANetzB.de)

## Requirements
- UNIX style Operating System
- bourne shell
- nc (netcat) or bash with net-redirections enabled
- MRTG

## Installation
- copy upnp2mrtg to your favourite place (/usr/local/bin/upnp2mrtg)
- install netcat
- check successful operation of upnp2mrtg
- modify your mrtg.cfg (add mrtg.cfg to your /etc/mrtg.cfg)
- check if MRTG is configured properly: is mrtg started from cron? check for /etc/cron.d/mrtg or use

        '''0-59/5 * * * *  /usr/bin/mrtg --logging /var/log/mrtg.log'''

## netcat
There are different incarnations of netcat. Type

'''nc -h'''

to check which on you use:

- The GNU Netcat http://sourceforge.net/projects/netcat (Version 0.7.1 , 2004-01-10)
- OpenBSD netcat http://www.openbsd.org/cgi-bin/cvsweb/src/usr.bin/nc/ (Version 1.97, 2010-05-19)
- netcat 1.10 http://www.unknown-site/netcat/ (Version 1.10 , 1996-03-20)
- ... or some other ...

## Configuration
If you use ...

### netcat 1.10

no configuration is required. (Create configuration file /etc/upnp2mrtg.cfg
with NETCAT="nc_q" or NETCAT="nc", if you have problems. There are some patched
netcat 1.10 around the world with -q Options, which i could'nt not find in the
original sources.)

### The GNU netcat

create configuration file /etc/upnp2mrtg.cfg with NETCAT="netcat".

### some other netcat
use -d Option to debug upnp2mrtg and drop me a note.

## Screenshot
Want to see the result?

## Download

    upnp2mrtg (2008-02-09)
    mrtg.cfg (2008-02-09)

## License

    GPL - GNU General Public License

## Links

- http://www.upnp.org
- http://www.wehavemorefun.de/fritzbox/
- http://www.avm.de
- FritzBox and MRTG at Google
- http://pywebsvcs.sourceforge.net/
- SOA and Web services at IBM
- Overview of Web services at www.jeckle.de
- SOAP Web services at DiveIntoPython.org
- http://www.oio.de/axis-soap.htm
- http://oss.oetiker.ch/mrtg/

## Todo

- curl for networking?
- Implementation with Python SOAPpy?
- uptime is not FritzBox uptime, it's online time
- Test it, with other upnp devices
- learn more about upnp/soap

compile bash with net-redirections enabled
download http://ftp.gnu.org/gnu/bash/bash-2.05b.tar.gz

'''
  ./configure --enable-net-redirections --disable-readline
  make
  cp bash /usr/local/bin/bash
  strip /usr/local/bin/bash
'''  
