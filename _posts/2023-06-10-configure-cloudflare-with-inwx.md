---
title: "Configuring Clouflare with INWX hosted domains"
excerpt_separator: "<!--more-->"
tags:
  - cloudflare
  - inwx
  - dns
  - domain
---

# Replacing the nameservers as Cloudflare suggests

https://www.inwx.de/en/nameserver

> ns.inwx.de
> ns3.inwx.eu
> ns2.inwx.de

Becomes:

> foo.ns.cloudflare.com
> bar.ns.cloudflare.com

# Additionally: Adding External Nameservers in the adminpanel

https://www.inwx.de/en/domainlist

1. Cogwheel -> External Nameservers
2. "external Nameserver"
3. Add the two nameservers as above
4. Save and close