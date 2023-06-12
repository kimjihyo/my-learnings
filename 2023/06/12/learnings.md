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

osxkeychain is the default credential helper on Mac, and it ask you to enter github username and password on the command prompt. You need to enter your personal access token for the password since password authentication has been removed.

In order to check what credential helper is being used, run the following command.
`git config credential.helper`

Once you install Git Credential Manager, the next time you clone an HTTPS URL that requires authentication, Git will prompt you log in using a browser window.

### SSH
If you authenticate with GitHub CLI, the CLI will find SSH public keys on your machine and will prompt you to select one for upload. If GitHub CLI does not find a SSH public key for upload, it can generate a new SSH public/private keypair and upload the public key to your account on GitHub. Then you can either authenticate with a personal access token or via the web browser.

If you authenticate without GitHub CLI, you will need to generate an SSH public/private keypair on your local machine and add the public key to your account on GitHub. Every time you use Git to authenticate with GitHub, you'll be prompted to enter your SSH key passphrase, unless you've stored the key.



# Switching Github accounts in terminal

# Signing commits