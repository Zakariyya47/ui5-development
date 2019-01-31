# Norms for UI5 development

## Source code version control

- All UI5 apps must use Git and be pushed to [BMW's Bitbucket instance](https://atc.bmwgroup.net/bitbucket).
- The app root directory name, and the repository name, must be identical to the UI5 app component, i.e. that last part of the component namespace.

## Code rules

- All JavaScript code must pass the rules in the [template `.eslintrc`](https://atc.bmwgroup.net/bitbucket/projects/FG5215UI5/repos/generator-ui5/browse/generators/app/templates/eslintrc).

## Code conventions

File locations and naming

- Project / development environment files in repository root
- Source code in `webapp` directory
- Controllers named `webapp/controller/ViewName.controller.js`
- Views named `webapp/view/ViewName.view.xml`

JavaScript

- Hungarian notation for variables
- No use of `global` / `window` scope
