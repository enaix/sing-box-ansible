# sing-box xray playbook

## Variables

Set IPs/hostnames of your servers in `inventory.ini`

`config.yml` has the following format:

```yaml
dns_ip: "1.1.1.1" # - ip address of the dns server

xray: # VLESS + xtls
  enabled: true
  port: 10134

trojan:
  enabled: false
  port: 10130

users:
  - name: "root"
    password: "PASSWORD"

reality: # Only needed for xray
  server: "telegram.org" # Server destination (sni)
  port: 443 # Server port
  short_id: "DEADBEEF"
```

Reality settings are available here: https://sing-box.sagernet.org/configuration/shared/tls/#reality-fields


## Running

Installation:

`ansible-playbook -i inventory.ini install.yaml -u root -k`

Configuration:

`ansible-playbook -i inventory.ini server.yaml -u root -k`
