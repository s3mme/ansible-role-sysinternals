# ansible-role-sysinternals

This role installs the SysInternals Suite

## Requirements

```
- name: ansible.windows
- name: community.windows
```

## Role Variables

| Variable                   | Default                                                         | Description                                                                  |
| -------------------------- | --------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `sysinternals_tools_path`  | `C:\Tools\`                                                     | Base path where tools are stored                                             |
| `sysinternals_url`         | `https://download.sysinternals.com/files/SysinternalsSuite.zip` | Download URL for the SysInternals Suite zip                                  |
| `sysinternals_path`        | `{{ tools_path }}\SysInternals`                                 | Installation path for the SysInternals Suite                                 |
| `sysinternals_add_to_path` | `true`                                                          | Whether to add the SysInternals path to the system PATH                      |
| `sysinternals_accept_eula` | `true`                                                          | Whether to automatically accept the EULA for SysInternals tools via registry |

## Dependencies

None.

## Example Playbook

```yaml
- hosts: windows_servers
  roles:
    - role: ansible-role-sysinternals

- hosts: windows_servers
  roles:
    - role: ansible-role-sysinternals
      vars:
        sysinternals_tools_path: "D:\\Tools\\"
        sysinternals_add_to_path: false
        sysinternals_accept_eula: false
```

## License

MIT

## Author Information

- [s3mme.com](https://s3mme.com/)
