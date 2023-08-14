[![CI](https://github.com/de-it-krachten/ansible-role-azure_cli/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-azure_cli/actions?query=workflow%3ACI)


# ansible-role-azure_cli

Installs the azure cli on a variety of platforms



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 10 (Buster)<sup>1</sup>
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# List of extensions to install
azure_cli_extensions: []
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'azure_cli'
  hosts: all
  become: "yes"
  vars:
    azure_cli_extensions: [{'name': 'aks-preview'}, {'name': 'ssh', 'system': True}, {'name': 'image-copy-extension', 'version': '0.2.12'}]
  tasks:
    - name: Include role 'azure_cli'
      ansible.builtin.include_role:
        name: azure_cli
</pre></code>
