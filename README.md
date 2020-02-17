---
name: 'ansible-galaxy-role-skeleton'
about: 'Project template for Ansible Galaxy Roles.'
comments: true
feedback: true
---

# Ansible Galaxy Role Skeleton

## Description

Ansible Galaxy Role Skeleton is used to quickly create new Ansible Galaxy roles.

## Requirements

- Ansible 2.9+
- Python 3.4+

## Usage

#### Role Names

##### Roles long name

Used as the roles repository name in cases where you have a single role per repository.

```shell
ansible-role-%{specific_role}
```

##### Roles short name

Used when creating a new role using this project.:

```shell
%{specific_role}
```

### Setup

#### Clone project fork

Clone your customised personal or business fork to your Ansible projects directory

```shell
mkdir ~/projects
cd ~/projects
git clone git@gitlab.cherubits.hu:oss/ansible-galaxy-roles/ansible-galaxy-role-skeleton.git
export ALTERNATIVE_ROLE_SKELETON_PATH=~/projects/ansible-galaxy-role-skeleton
```

#### Create your role

##### Syntax example

```shell
ansible-galaxy init --role-skeleton=ALTERNATIVE_ROLE_SKELETON_PATH %{specific_role}
```

#### Real world usage examples:

##### To create a new role

```shell
mkdir -p ~/projects/ansible-%{specific_project}-playbook/roles
cd ~/projects/ansible-%{specific_project}-playbook/roles
ansible-galaxy init --role-skeleton=~/projects/ansible-galaxy-role-skeleton/skeleton %{specific_role} -vvv
```

##### To overwrite an existing role

```shell
cd ~/projects/ansible-galaxy-role-skeleton/roles
ansible-galaxy init --role-skeleton=~/projects/ansible-galaxy-role-skeleton/skeleton -f %{short-name-of-existing-role} -vvv
```

##### Set up Molecule environment

```shell script
virtualenv --python=/usr/bin/python3.7 .env
source .env/bin/activate
pip install molecule docker molecule[lint] molecule[docker]
```

##### Set up your default Molecule scenario

```shell
molecule init scenario -s default -d lxd -r %{short-name-of-role}
```

## Troubleshooting

### Molecule

#### pytest bug: Fix for error"AttributeError: 'Config' object has no attribute 'cache'

* [Possible bug with the 3.10.0 release #4304](https://github.com/pytest-dev/pytest/issues/4304)

```shell
touch molecule/default/pytest.ini" like this one.
```

```ini
[pytest]
addopts = -p no:cacheprovider -p no:stepwise
```

## Author(s)

- [László Hegedűs](mailto:laszlo.hegedus@cherubits.hu)
- [Christopher Steel](mailto:christopher.steel@mcgill.ca)

## License 

[MIT](https://tldrlegal.com/license/mit-license)

