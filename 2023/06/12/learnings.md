# Authentication to Github

## About authentication to GitHub
You can access your resources in GitHub in a variety of ways: in the browser, via GitHub Desktop or another desktop application, with the API, or via the command line. Each way of accessing GitHub supports different modes of authentication.
- Username and password with two-factor authentication
- Personal access token
- SSH Key

## Authenticating with the command line
You can access repositories on GitHub from the command line in two ways, HTTPS, and SSH, and both have a different way of authenticating. The method of authenticating is determined based on whether you choose an HTTPS or SSH remote URL when you clone the repository.

### HTTPS
If you authenticate with GitHub CLI ([gh](https://cli.github.com/)), you can either authenticate with a personal access token or via the web browser. Password-based authentication for Git has been removed in favor of more secure authentication methods. Every time you use Git to authenticate with Github, you'll be prompted to enter your credentials to authenticate with GitHub, unless you cache them with a credential helper such as GitHub CLI, Git Credential manager and osxkeychain.

In order to check what credential helper is being used, run the following command.
`git config credential.helper`

It is recommended to use SSH or upgrade to the Git Credentiual Manager (GCM) GCM can manage authentication on your behalf (no more manual personal access tokens) including two-factor authentication.






### SSH



# Switching Github accounts in terminal

# Signing commits