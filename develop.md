# Working on a UI5 app

> Remember to first [Set up your local UI5 development environment](./setup.md).

## Create a new app

1. Scaffold the app

  > The folder must be named identical to the UI5 app component, i.e. the last part of the component namespace.

  ```bash
  mkdir some-app
  cd some-app
  yo ui5
  ```

  > This will generate a basic UI5 app, ready for running locally (with remote OData), linting, build, deployment, etc.

2. Create an empty Bitbucket repository, named identical to the app project folder, in a suitable Bitbucket project.

  > Initially, the [`fg5215ui5` Bitbucket project](https://atc.bmwgroup.net/bitbucket/projects/FG5215UI5) can be used.

3. Connect your local app repository to the Bitbucket repository:

  ```bash
  cd some-app
  git remote add origin https://your-user@atc.bmwgroup.net/bitbucket/scm/some-bitbucket-project/some-app.git
  git push -u origin master
  ```

## Upgrade an existing app

> `webapp/Component.js` should exist.

```bash
cd some-app
yo ui5
```

> This will update the app to the latest setup for running locally, linting, build, deployment, etc.

## Make changes to an app

> Ensure you are working in the correct Git branch, that you commit frequently, and that commits are small, well-crafted, self-contained changes.

To serve the app locally (with remote OData) while developing, run:

```bash
cd some-app
npm start
```
> This also enables running the UI5 Demo Kit locally for easy access to the documentation in the correct version.

> **SSO Errors** The first OData request will have an SSO redirect that will cause a CORS error. Click on the URL shown with the error in the Console. This will authenticate your user, and prevent further CORS issues while your session stays alive.

Before committing your changes, check that there are no linting errors and that the build process still works:

```bash
npm run check
```

> This will list static code analysis errors that you need to fix before committing, build the app to `dist/` so that you can fix any build issues if needed, and serve the built app so that your can open it to test.
