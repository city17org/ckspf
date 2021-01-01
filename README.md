## ckspf
**ckspf** is a small script used to walk the DNS TXT record for a domain and
recursively lookup and print the IP addresses referenced in the SPF policy.

Useful for whitelisting domains whose SMTP servers do not play nicely with
greylisting or other anti-spam techniques, or to check records with multiple
levels of redirection.

### Dependencies
Requires [dig](https://www.isc.org/downloads/bind/)

### Usage

	$ ./ckspf
	usage: ckspf domain
	$ ./ckspf outlook.com
	157.56.232.0/21
	157.56.240.0/20
	207.46.198.0/25
	207.46.4.128/25
	...

### Caveats
Not fully RFC 7208 compliant. Only supports the a, mx, ip4, ip6 and include
mechanisms, and redirect modifier.
