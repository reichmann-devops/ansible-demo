# ansible-demo

The ansible-demo.yml playbook will clone a repo to a targed host then push the content to a remote host(s).

The simple_script.sh will run on all remote hosts in the inventory and display the output from the script.

Final step is to clean up the cloned repo from the /tmp directory on targeted and remote hosts.

## Local files

Ansible config with minimum requiements to run locally with ansible-playbook

Example inventory.yml with 4 managed hosts

Ansible vault encrypted vars.yml file with the following variables:

    - private_key: contents from the ssh key used to access GitHub
    - gh_username: GitHub user name for https connections
    - gh_readhonly_pat: Personal Access Token with read only rights to the repositories

Example usage:

    ```bash
    # Run against all hosts in the inventory
    ansible-playbook pull_copy_git_repo.yml --ask-vault-pass
    ```

## Notes

Ansible Automation Platform will require vault credentials to decrypt the vars.yml file

This has been tested in AAP 2.5+ and will work with the default execution environment.
