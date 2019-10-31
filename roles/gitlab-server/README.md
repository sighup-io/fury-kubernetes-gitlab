# Gitlab Server Ubuntu 18


# Usage
playbook.yml
```yaml
- hosts: gitlab example
  roles:
    - role: gitlab/gitlab-server
      display_name: 'Example'
      external_url: 'https://git.example.io'
      gitlab_version: 11.7.0-ce.0
      git:
        folder: '/mnt/data/repo'
      backup:
        backup_keep_time: 604800
        provider: 'AWS'
        region: '<your-region>'
        aws_access_key_id: '<your-access-key-id>'
        aws_secret_access_key: '<your-secret-access-key>'
        bucket: 'gitlab-exmple-backups'
      ldap:
        enable: true
        label: 'LDAP'
        host: '<your-ldap-server>'
        port: 389
        uid: 'sAMAccountName'
        bind_dn: '<the-full-dn-of-the-user-you-will-bind-with>'
        password: '<the-password-of-the-bind-user>'
        encryption: 'plain' # "start_tls" or "simple_tls" or "plain"
        base: '<base-path>'
        user_filter: '<query-filter<bind-dn-of-user-to-query-ldap>'
      registry:
	enable: true
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
      letsencrypt:
        enable: true
```
