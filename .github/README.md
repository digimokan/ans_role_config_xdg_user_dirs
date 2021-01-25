# ans_role_config_xdg_user_dirs

Create and configure
[XDG User Directories](https://www.freedesktop.org/wiki/Software/xdg-user-dirs/)
for a user.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_xdg_user_dirs.svg?label=release)](https://github.com/digimokan/ans_role_config_xdg_user_dirs/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.txt "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Create the traditional XDG User Directories ('Documents', 'Pictures,
  'Desktop', etc) for a user.
* Configure the settings-files that many applications look for to access the
  XDG User Directories.

## Supported Operating Systems

* Arch Linux.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_xdg_user_dirs
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Create and configure XDG User Dirs for user2"
         ansible.builtin.include_role:
           name: ans_role_config_xdg_user_dirs
         vars:
           user_name: "user2"
   ```

## Role Options

See the role `defaults` file, for overridable vars:

  * [defaults/main.yml](../defaults/main.yml)

Define these _required_ vars for the role:

  * `user_name`: user login name to configure the XDG user dirs for

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_xdg_user_dirs/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

