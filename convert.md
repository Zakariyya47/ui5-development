# Convert a legacy UI5 app

> These steps should be executed for UI5 apps that were previously uploaded to an ABAP server and that do not have a relevant `package.json` file.

1. Put the app files (download from ABAP server with Eclipse or with report `/UI5/UI5_REPOSITORY_LOAD`) in a suitably named project root directory inside your `repositories` directory, for example `repositories/some-app`.

> The folder must be named identical to the UI5 app component, i.e. that last part of the component namespace.

2. Initialize a Git repository in the project root directory:

  ```bash
  cd some-app
  git init
  git add --all
  git commit -m "Files from ABAP server"
  ```

3. Rename the `WebContent` folder to `webapp`.

4. Ensure `"sap.app": {"id": "<component namespace>"}` is maintained in `manifest.json`.

5. Update the project using our UI5 Yeoman generator:

  ```bash
  yo ui5
  ```

  > This will generate files needed for running the app locally, linting, build and deployment, etc.

6. View the changes made above in your favorite graphical Git client, test the app, and then commit the changes with a message like 'Prepare for CI and running locally'.

7. Create an empty Bitbucket repository, named identical to the app project folder, in a suitable Bitbucket project.

  > Initially, the [`fg5215ui5` Bitbucket project](https://atc.bmwgroup.net/bitbucket/projects/FG5215UI5) can be used.

8. Connect the local repository to the Bitbucket repository (from the project root directory):

  ```bash
git remote add origin https://your-user@atc.bmwgroup.net/bitbucket/scm/some-bitbucket-project/some-app.git
git push -u origin master
```
