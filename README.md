# UI5 Development at FG-5215

Notes, norms, processes, and procedures for developing SAPUI5 / OpenUI5 apps.


> **Command Prompt / Bash if using Windows**
>
> Use "Git for Windows Bash", which should be available after installing "Git for Windows" from WUSS.

## BMW proxy and NPM

`npm install` requires proxy information, including credentials, for BMW intranet's proxy. These credentials are provided in the bash prompt, and it is thus important to clear the bash history, so that the plain text password is not stored in a file.

Before using `npm install`:

```bash
npm config set proxy http://user:pwd@proxy.w9:80
npm config set https-proxy http://user:pwd@proxy.w9:80
```

> If your password contains a '$', use a backslash to escape it, e.g. 'mypas\\$' if your password is 'mypas$'.

Clean up plain text passwords afterward:

```bash
npm config delete proxy
npm config delete https-proxy
history -c
exit
```

## Documentation

- [Norms for UI5 development](./norms.md)
- [Set up your local UI5 development environment](./setup.md)
- [Convert a legacy UI5 app](./convert.md)
- [Working on a UI5 app](./develop.md)
- [Build and deploy a UI5 app](./deploy.md)

## Open Items

For discussion and decision.

### UI5 Inspector Chrome Extension

The [UI5 Inspector Chrome Extension](https://chrome.google.com/webstore/detail/ui5-inspector/bebecogbafbighhaildooiibipcnbngo) makes debugging much quicker, but is not accessible behind BMW firewall.

### NPM installations behind proxy

Currently, in order to install NPM packages, your q-user password need to be entered in visible text in the command prompt? Is this okay?

### Public Node.js libraries

[NPM](https://www.npmjs.com/) registry access is technically possible by setting NPM proxy config including credentials. However, we need to clarify the BMW policy position on using Node.js public NPM packages.

### Build and deploy pipeline

We need to decide between 2 general options:

- Automated on Jenkins. See [example best practice](https://developers.sap.com/tutorials/ci-best-practices-fiori-abap.html).
- Manual on developer machine using SAP's [UI5 Tooling](https://github.com/SAP/ui5-tooling).
