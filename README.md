Ansible role: dotfiles
=========

Installs a set of dotfiles or other local config files to a home directory.

Requirements
------------

Requires `git` and a repository containing the dotfiles.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    dotfiles_repo_url: https://github.com/jrgoldfinemiddleton/dotfiles.git
    dotfiles_repo_version: master

The git repository and branch/tag/commit hash to use for retrieving dotfiles. Dotfiles should generally be laid out within the root directory of the repository.

    dotfiles_repo_accept_hostkey: no

Add the hostkey for the repo url if not already added. If ssh_opts contains "-o StrictHostKeyChecking=no", this parameter is ignored.

    dotfiles_repo_local_dest: ~/Developer/dotfiles

The local path where the `dotfiles_repo` will be cloned.

    dotfiles_home: ~

The home directory where dotfiles will be linked. Generally, the default should work, but in some circumstances, or when running the role as sudo on behalf of another user, you may want to specify the full path.

    dotfiles_files:
      - .bash_profile
      - .gitignore
      - .inputrc
      - .vimrc

Which files from the dotfiles repository should be linked to the `dotfiles_home`.



A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - { role: jrgoldfinemiddleton.dotfiles }

License
-------

MIT

Author Information
------------------

This role was created in 2018 by Jason Goldfine-Middleton as a fork of [Jeff Geerling](https://www.jeffgeerling.com/)'s [role of the same name](https://github.com/geerlingguy/ansible-role-dotfiles).
