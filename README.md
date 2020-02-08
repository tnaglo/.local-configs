# .local-configs

.tmux.conf.local .zshrc.local .vimrc.local

## ToDo

- [ ] Switch to new role (TDB) instead of [tnaglo.ansible_role_unix_user_env](https://galaxy.ansible.com/tnaglo/ansible_role_unix_user_eqnv)

## Usage

There are multiple ways to use this repository:

- source the local config files in your "main" configs (`source ~/.local-configs/.zshrc.local`)
- symlink the needed local config files so they are located where most configs would look for them (`ln -s ~/.local-configs/.zshrc.local ~/.zshrc.local`)
- use it in the ansible galaxy role tnaglo.unix_user_env_users like this:

  ```yaml
  - role: tnaglo.unix-user-env
    unix_user_env_users:
      - name: your_unix_username
        comment: 'your comment'
        shell: '/bin/zsh'
        tmux_config_repo: 'https://github.com/gpakosz/.tmux' # git url to the repo of my fav .tmux config
        local_configs_repo: 'https://github.com/tnaglo/.local-configs.git' # git url to the repo with my own local configs for tmux zsh and vim
  ```
