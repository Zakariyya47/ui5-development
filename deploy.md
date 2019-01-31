# Build and deploy a UI5 app

## Maintain an app's deployment settings

Settings should be maintained in `bmw-ui5.yaml`.

For example, the Workbench Request to be used can be maintained at `FES_TRANSPORT`.

## Deploy an app

```bash
cd some-app
npm run deploy
```

> This process includes linting (static code analysis), building to `dist/`, and deploying `dist/` to an ABAP BSP Container. It will fail if there are linting errors.
