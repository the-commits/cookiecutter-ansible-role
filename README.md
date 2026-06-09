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
| `license` | `AGPL-3.0` | License type |
| `create_molecule` | `yes` | Scaffold molecule tests |
| `mirror_to_github` | `yes` | Auto-create public GitHub mirror |
| `secret_uuid` | *(sr.ht secret UUID)* | build.sr.ht secret for GitHub PAT |

When `mirror_to_github` is `yes`, the template generates a `.builds/push.yml`
for automated GitHub mirroring and runs `gh repo create --public` to set up
the mirror repo.

## Output

```
my_role/
├── .builds/          # GitHub mirror build manifest (if mirror_to_github)
├── .github/          # Issue/PR redirects to sourcehut
├── defaults/
├── handlers/
├── meta/
├── tasks/
├── templates/
├── vars/
├── molecule/default/
├── galaxy.yml
├── AGENTS.md
├── CONTRIBUTING.md   # Points contributors to sourcehut
├── CHANGELOG.md
├── LICENSE
└── README.md
```

## Related Templates

- **`cookiecutter-ansible-role`** (this repo) — for standalone roles (system config, SSH, etc.)
- **`cookiecutter-ansible-docker-compose-role`** — for roles that deploy Docker Compose stacks.
  Use this when your role deploys containers via `docker compose`. It includes default
  resource limits (512 MB RAM, 1 vCPU) and `deploy.resources` in the generated compose file.

## Requirements

- Python 3.8+
- [cookiecutter](https://cookiecutter.readthedocs.io/) (`pip install cookiecutter`)
- Molecule + vagrant-libvirt (for testing generated roles)
