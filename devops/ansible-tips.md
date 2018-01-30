# Ansible Tips

## Filters For Formatting Data

You can convert some variable to json or yaml.

- http://docs.ansible.com/ansible/latest/playbooks_filters.html#filters-for-formatting-data

```
{{ some_variable | to_json }}
{{ some_variable | to_yaml }}
```

```
tasks:
  - shell: cat /some/path/to/file.json
    register: result

  - set_fact: myvar="{{ result.stdout | from_json }}"
```