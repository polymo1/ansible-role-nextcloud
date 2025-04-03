# syncthing

Ansible role to install and configure syncthing. Fork of github.com:rolehippie/syncthing

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [syncthing_arch](#syncthing_arch)
  - [syncthing_extra_users](#syncthing_extra_users)
  - [syncthing_general_users](#syncthing_general_users)
  - [syncthing_keyring](#syncthing_keyring)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### syncthing_arch

Architecture for syncthing repo

#### Default value

```YAML
syncthing_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64' }}"
```

### syncthing_extra_users

List of extra users to configure

#### Default value

```YAML
syncthing_extra_users: []
```

#### Example usage

```YAML
syncthing_extra_users:
  - username: hans
    config:
      device:
        '@introducer': True
        autoAcceptFolders: True
      gui:
        address: 0.0.0.0:8384
  - username: foobar
    home: /var/lib/foobar
```

### syncthing_general_users

List of general users to configure

#### Default value

```YAML
syncthing_general_users: []
```

#### Example usage

```YAML
syncthing_general_users:
  - username: hans
    config:
      device:
        '@introducer': True
        autoAcceptFolders: True
      gui:
        address: 0.0.0.0:8384
  - username: foobar
    home: /var/lib/foobar
```

### syncthing_keyring

Path for the repository keyring

#### Default value

```YAML
syncthing_keyring: /usr/share/keyrings/syncthing-archive-keyring.gpg
```

## Discovered Tags

**_syncthing_**


## Dependencies

- None

## License

Apache-2.0

## Authors
[Wesley Bryie](https://wesbryie.com), [sr.ht](https://sr.ht/~polymo1)
Original Author: [Thomas Boerger](https://github.com/tboerger)
