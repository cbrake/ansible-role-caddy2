# Caddy2 Ansible Role

## Example use in playbook

```
- name: My server
  hosts: servername
  become: yes
  roles:
    - role: caddy2
      tags: caddy2
      caddy2_config: |
        portal.myserver.us {
          reverse_proxy localhost:8081
        }

        graphs.myserver.us {
          reverse_proxy localhost:3001
        }
```

## Notes

Caddy puts downloaded certs in `$HOME/.local/share/caddy/`. `$HOME` is typically
`/home/caddy2`.
