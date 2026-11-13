# alu-webstack

Web infrastructure project work for African Leadership University.

## https_ssl

HTTPS and SSL termination for `ephremnziza.tech`.

| File | Description |
|---|---|
| `0-world_wide_web` | Bash script that audits DNS records of a domain and its subdomains (`www`, `lb-01`, `web-01`, `web-02`) using `dig` and `awk` |
| `1-haproxy_ssl_termination` | HAProxy config on lb-01 that terminates SSL on port 443 for `www.ephremnziza.tech` and balances traffic between web-01 and web-02 |
| `2-redirect_http_to_https` | HAProxy config that also redirects HTTP traffic to HTTPS with a 301 |

### Usage

```bash
./0-world_wide_web ephremnziza.tech          # all four subdomains
./0-world_wide_web ephremnziza.tech web-02   # one subdomain
```

### Servers

| Name | Role | IP |
|---|---|---|
| 7380-web-01 | web server | 35.177.53.215 |
| 7380-web-02 | web server | 13.40.95.4 |
| 7380-lb-01 | HAProxy load balancer | 18.175.244.5 |

### Author

Ephrem Nziza
