# Gitlab Server Ubuntu 18


# Usage
playbook.yml
```yaml
- hosts: gitlab example
  roles:
    - role: gitlab
      display_name: 'Example'
      external_url: 'https://git.example.io'
      gitlab_version: 11.7.0-ce.0
      git:
        folder: '/mnt/data/repo'
      backup:
        bucket: 'gitlab-example-backups'
      registry:
        url: 'https://reg.example.io'
        host: reg.example.io
        port: 5000
        bucket_name: 'gitlab-example-registry'
      smtp:
        address: "smtp.example.org"
        port: "587"
        username: "username@example.io"
        password: "example-password"
        domain: "example.io"
        auth: "plain"
```