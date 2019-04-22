# Dep

## Configure

To configure dep with `ssh`

1. Add the ssh key to your keychain

   ```bash
   ssh-add -K ~/.ssh/id_rsa
   ```

   [Source](https://github.com/golang/dep/issues/1778)

2. Configure git so that it always clones via ssh

    ```bash
    git config --global url."git@github.com:".insteadOf "https://github.com/"
    ```

    Which adds the following to your global gitconfig

    *~/.gitconfig*

    ```text
    [url "git@github.com:"]
        insteadOf = https://github.com/
    ```

    [Source](https://github.com/golang/dep/blob/master/docs/FAQ.md#how-do-i-get-dep-to-authenticate-via-ssh-to-a-git-repo)