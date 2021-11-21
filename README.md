# Typescript 4.5 Regression

I recently upgraded one of my projects to TypeScript 4.5 and it breaks if the underlying package has defined export map.

I am sharing this repo which demonstrates the issue in isolation.

- The repo has two sub-directories. `package` and `app`.
- The `package` defines the export map along with `types` key inside the `package.json` file. The types exports an ambient module.
- The `app` installs the `package` and imports the ambient module.
- Running `npm run build` fails if the `app` is using `typescript@4.5`. However compiles fine if using `typescript@4.4`.