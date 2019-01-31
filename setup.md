# Set up your local UI5 development environment

> Note that IDE and graphical git client response times are better if the local repositories are stored in a non-network location, e.g. `C:/Users/Q-/Development`. As long as you are disciplined and commit and push frequently, this should not be an issue.

> **Remember to set and clean up the proxy information**. See [BMW proxy and NPM](./README.md).

1. Install Node.js and Git from [WUSS](https://wuss.bmwgroup.net).

2. Install Grunt, then Yeoman and our UI5 Yeoman Generator globally:

  ```bash
  npm install --global grunt
  npm install --global yo git+https://atc.bmwgroup.net/bitbucket/scm/fg5215ui5/generator-ui5.git
  ```

  > **Always clear the history and then close the bash session after using plain text passwords**:
  > ```
  > history -c
  > exit
  > ```

3. Create directories for your local repository clones, and UI5 library resources respectively:

  ```bash
  cd your-local-development-directory
  mkdir repositories resources
  ```

4. Download required SDKs from https://tools.hana.ondemand.com/#sapui5 and extract to the `resources` directory.

5. Set up an editor (optional)

  - [Enabling linting](https://eslint.org/docs/user-guide/integrations) will make adhering to code rules much easier.
  - [Enabling EditorConfig support](https://editorconfig.org/#download) will make code tidier.

Example directory structure:

```
resources
  sapui5-sdk-1.38.39
repositories
  some-app
  ui5-development
```

> The reason for this rigid directory structure, is so that all app projects can use the same settings for relative paths to shared resources.
