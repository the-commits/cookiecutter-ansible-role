# cookiecutter-ansible-role

A [cookiecutter](https://github.com/cookiecutter/cookiecutter) template for
scaffolding Ansible roles following tjenamors conventions.

## Usage

```bash
pip install cookiecutter
cookiecutter git@git.sr.ht:~the-commits/cookiecutter-ansible-role
```

You'll be prompted for:

| Prompt | Default | Description |
|---|---|---|
| `role_name` | `my_role` | Role name (snake_case) |
| `namespace` | `tjenamors` | Galaxy namespace (org) |
| `author` | `the-commits` | Maintainer name |
| `description` | `An Ansible role to ...` | Short description |
| `min_ansible_version` | `2.14` | Minimum Ansible version |
| `git_host` | `git.sr.ht` | Git hosting provider domain |
| `git_user` | *(author)* | User/org on the git host |
| `license` | `MIT` | License type |
| `create_molecule` | `yes` | Scaffold molecule tests |

## Output

```
my_role/
├── defaults/
├── handlers/
├── meta/
├── tasks/
├── templates/
├── vars/
├── molecule/default/
├── galaxy.yml
├── AGENTS.md
├── CHANGELOG.md
├── LICENSE
└── README.md
```

## Requirements

- Python 3.8+
- [cookiecutter](https://cookiecutter.readthedocs.io/) (`pip install cookiecutter`)
- Molecule + vagrant-libvirt (for testing generated roles)
