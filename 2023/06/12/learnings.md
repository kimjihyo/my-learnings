# Authentication to GitHub

## About authentication to GitHub
You can access your resources in GitHub in a variety of ways: in the browser, via GitHub Desktop or another desktop application, with the API, or via the command line. Each way of accessing GitHub supports different modes of authentication.
- Username and password with two-factor authentication
- Personal access token
- SSH Key

## Authenticating with the command line
You can access repositories on GitHub from the command line in two ways, HTTPS, and SSH, and both have a different way of authenticating. The method of authenticating is determined based on whether you choose an HTTPS or SSH remote URL when you clone the repository.

### HTTPS
If you authenticate with GitHub CLI ([gh](https://cli.github.com/)), you can either authenticate with a personal access token or via the web browser. Password-based authentication for Git has been removed in favor of more secure authentication methods. Every time you use Git to authenticate with Github, you'll be prompted to enter your credentials to authenticate with GitHub, unless you cache them with a credential helper such as [GitHub CLI](https://cli.github.com), [Git Credential Manager](https://github.com/git-ecosystem/git-credential-manager) and osxkeychain.

osxkeychain is the default credential helper on Mac, and it prompts you to enter github username and password on the command line. You need to e nter your personal access token for the password since password authentication has been removed.

In order to check what credential helper is being used, run the following command.
`git config credential.helper`

Once you install Git Credential Manager, the next time you clone an HTTPS URL that requires authentication, Git will prompt you log in using a browser window.

### SSH
If you authenticate with GitHub CLI, the CLI will find SSH public keys on your machine and will prompt you to select one for upload. If GitHub CLI does not find a SSH public key for upload, it can generate a new SSH public/private keypair and upload the public key to your account on GitHub. Then you can either authenticate with a personal access token or via the web browser.

If you authenticate without GitHub CLI, you will need to generate an SSH public/private keypair on your local machine and add the public key to your account on GitHub. Every time you use Git to authenticate with GitHub, you'll be prompted to enter your SSH key passphrase, unless you've stored the key. 


# Storing Credentials per Repository in Git Credential Manager

## Add your username/PAT in the hostname
You (a physical person) may have one or more user accounts (identities) with one or more Git hosting providers. Since most Git hosts don't put a "user" part in their URLs, by default, Git will treat the user part for a remote as the empty string. If you have multiple identities on one domain, you'll need to insert a unique user part per-identity yourself.

There are good reasons for having multiple identities on one domain. You might use one GitHub identity for your personal work, another for your open source work, and a third for your employer's work. You can ask Git to assign a different credential to different repositories hosted on the same provider. HTTPS URLs include an optional "name" part before an `@` sign in the domain name, and you can use this to force Git to distinguish multiple users. This should likely be your username on the Git hosting service, since there are cases where GCM will use it like a username.

use: `https://kimjihyo@github.com/kimjihyo/repo.git` \
instead of: `https://github.com/kimjihyo/repo.git`

## useHttpPath for the host
Git Credential Manager can select a credential baased on the full URL, rather than sharing them by hostname.

### All repositories on the remote host
```
git config --global credential.useHttpPath true
```

### Just one repository on the remote host
```
git config credential.useHttpPath true
```

# `source` Command

## What is it?
`source` is a shell built-in command which is used to read and execute the content of a file, passwed as an argument in the current shell script.

## Difference between executing a script and sourcing it
both sourcing and executing the script will run the commands in the script line by line, as if you typed those commands by hand line by line.

The differences are
- When you execute the script you are opening a new shell, type the commands in the new shell, copy the output back to your current shell, then close the new shell. Any changes to environment will take effect only in the new shell and will be lost once the new shell is closed.
- When you source the script you are typing the commands in your current shell. Any changes to the environment will take effect and stay in your current shell.

# .zprofile, .zshrc, .zlogin - What goes where?

## `.zprofile`
`.zprofile` and `.zlogin` are basically the same thing. they set the environment for login shells. But they get loaded at different times. Apple does things a little differently. Terminal initially opens both a login and interactive shell even though you don't authenticate. However, any subsequent shells that are opened are only interactive.