# ansible-demo

This is an xample playbook that will clone this repo to `localhost` then push the content to a remote host.

The simple_script.sh will run on remote host(s) and display the output from the script.

Final step is to clean up the cloned repo from the /tmp directory on both localhost and remote host.

Example inventory with 4 RHEL hosts

vars:
    - target_hosts: host that will run the script locally, defaults to all servers in inventory
    - ansible_user: set in the ansible.cfg

Example usage:

```bash
# Run against all hosts in the inventory
ansible-playbook pull_copy_git_repo.yml
```

```bash
# Run against specific hosts/group
ansible-playbook pull_copy_git_repo.yml --extra_vars target_hosts=rhel01,rhel02
```

```bash
# Run against single host
ansible-playbook pull_copy_git_repo.yml --extra_vars target_hosts=rhel03
```

## Notes

This has been tested in AAP 2.5+ and will work with the default execution environment.
