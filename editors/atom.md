# Recommended setup for [Atom](https://atom.io/)

The [`linter-eslint`](https://atom.io/packages/linter-eslint) plugin shows linting errors proactively in the editor.

## BMW proxy

Before installing plugins, set the proxy information and credentials:

```bash
apm config set https-proxy http://user:password@proxy.w9:80
```

> If your password contains a '$', use a backslash to escape it, e.g. 'mypas\$' if your password is 'mypas$'. 

After installing, **delete the proxy configuration and clear the bash history**, so that your plain text password is not stored:

```bash
apm config delete https-proxy
history -c
exit
```

## Install plugins

1. Install the plugins:
  ```bash
  apm install linter-eslint
  ```

2. Restart Atom.

3. Approve the installation of dependencies (there may be a sequence of prompts in Atom).

4. Restart Atom again once all dependencies are installed.
