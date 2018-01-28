# role-icecast
ansible role for icecast server

## Example Playbook

    - hosts: stream-server
      vars_files:
        - vars/icecast.yml
      roles:
        - role-icecast

## Example vars/icecast.yml

    ---
    icecast_location: Paris, France
    icecast_admin: icemaster@mydomain.com

    icecast_limits_clients: 5000
    icecast_limits_sources: 10

    icecast_authentication_source_password: source_password
    icecast_authentication_relay_user: relay
    icecast_authentication_relay_password: relay_password
    icecast_authentication_admin_user: admin
    icecast_authentication_admin_password: admin_password

    icecast_hostname: stream.mydomain.com

    icecast_listen_socket_port: 8000
    icecast_listen_socket_bind_address: 127.0.0.1

    # List of mounts to define.
    icecast_mounts:
      # For valid mount options, see:
      # http://icecast.org/docs/icecast-2.4.1/config-file.html#mountsettings
      - mount-name: /rock-128.mp3
        fallback-mount: /backup-128.mp3
        fallback-override: 1
      - mount-name: /rock-192.mp3
        fallback-mount: /backup-192.mp3
        fallback-override: 1
        username: premium
        password: hackmypremium

    icecast_log_level: info

## Licence

MIT / BSD

## Author Information

This role was created by François LASSERRE aka ChoiZ.
