# {{ cookiecutter.role_name.replace('_', ' ') | title }}

{{ cookiecutter.description }}

## Requirements

- Ansible {{ cookiecutter.min_ansible_version }}+
- `ansible.builtin` collection (included with Ansible)
- Root/sudo access on target hosts

## Installation

### From Ansible Galaxy (once published)

```bash
ansible-galaxy install {{ cookiecutter.namespace }}.{{ cookiecutter.role_name }}
```

### From source

Add to your `requirements.yml`:

```yaml
---
roles:
  - name: {{ cookiecutter.role_name }}
    src: git@{{ cookiecutter.git_host }}:{{ cookiecutter.git_user }}/{{ cookiecutter.role_name }}
    scm: git
    version: main
```

Then install:

```bash
ansible-galaxy install -r requirements.yml -p roles/
```

## Role Variables

All variables are prefixed with `{{ cookiecutter.role_name }}_`. See [`defaults/main.yml`](defaults/main.yml) for the full list.

| Variable | Default | Description |
|---|---|---|
| `{{ cookiecutter.role_name }}_example` | `value` | Description |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  become: true
  vars:
    {{ cookiecutter.role_name }}_example: value
  roles:
    - role: {{ cookiecutter.role_name }}
```

## Local Development

### Prerequisites

```bash
pip install molecule molecule-plugins[vagrant]
vagrant plugin install vagrant-libvirt
```

### Running Tests

```bash
molecule test
```

### Project Layout

```
.
├── defaults/        # Default variable values
├── handlers/        # Ansible handlers
├── meta/            # Galaxy metadata + supported platforms
├── tasks/           # Main role tasks
├── templates/       # Jinja2 templates
├── vars/            # OS-specific variables
├── galaxy.yml       # Galaxy metadata (for publishing)
├── README.md
└── CHANGELOG.md
```

## Contributing

1. Fork the repository on [{{ cookiecutter.git_host }}](https://{{ cookiecutter.git_host }}/~{{ cookiecutter.git_user }}/{{ cookiecutter.role_name }})
2. Create a feature branch
3. Make your changes
4. Run `molecule test` to verify
5. Open a pull request / send a patch

## License

{{ cookiecutter.license }} — see [LICENSE](LICENSE) for details.
