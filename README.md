# storage

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/storage)
[![General Workflow](https://github.com/rolehippie/storage/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/storage/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/storage/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/storage/actions/workflows/readme.yml)
[![Galaxy Workflow](https://github.com/rolehippie/storage/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/storage/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/storage)](https://github.com/rolehippie/storage/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.storage-blue)](https://galaxy.ansible.com/rolehippie/storage)

Ansible role to mount remote CIFS storage.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [storage_credentials](#storage_credentials)
  - [storage_dir_mode](#storage_dir_mode)
  - [storage_file_mode](#storage_file_mode)
  - [storage_gid](#storage_gid)
  - [storage_options](#storage_options)
  - [storage_password](#storage_password)
  - [storage_path](#storage_path)
  - [storage_server](#storage_server)
  - [storage_share](#storage_share)
  - [storage_uid](#storage_uid)
  - [storage_username](#storage_username)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`


## Default Variables

### storage_credentials

Path to credentials file

#### Default value

```YAML
storage_credentials: /etc/smbpasswd
```

### storage_dir_mode

Mode for directories

#### Default value

```YAML
storage_dir_mode: '0770'
```

### storage_file_mode

Mode for files

#### Default value

```YAML
storage_file_mode: '0660'
```

### storage_gid

Group for the mount

#### Default value

```YAML
storage_gid: root
```

### storage_options

Mount options for fstab

#### Default value

```YAML
storage_options:
  - noauto
  - nofail
  - x-systemd.automount
  - x-systemd.requires=network-online.target
  - x-systemd.device-timeout=10
  - vers=3.0
  - mfsymlinks
  - uid={{ storage_uid }}
  - gid={{ storage_gid }}
  - dir_mode={{ storage_dir_mode }}
  - file_mode={{ storage_file_mode }}
  - workgroup=workgroup
  - credentials={{ storage_credentials }}
```

### storage_password

Password for CIFS

#### Default value

```YAML
storage_password:
```

### storage_path

Path to mount to

#### Default value

```YAML
storage_path:
```

### storage_server

Server to connect via CIFS

#### Default value

```YAML
storage_server:
```

### storage_share

Share name of CIFS storage

#### Default value

```YAML
storage_share: backup
```

### storage_uid

User for the mount

#### Default value

```YAML
storage_uid: root
```

### storage_username

Username for CIFS

#### Default value

```YAML
storage_username:
```

## Discovered Tags

**_storage_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
