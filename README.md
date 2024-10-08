A list of repos publicly displayed on the [GoLaunch](https://golaunch.dev) create page.

# Submitting your repo for public use

#### Requirements

- A valid golaunch.yaml. View the instructions below on how to create and test your golaunch.yaml
- Your github repo must be marked as a template in its Github settings
- Someone from our team must manuallay review the repository to make sure everything is properly done

#### How to submit

Once you've verified and tested your template out at [the custom test page](https://golaunch.dev/custom) you can create a merge request on this repo detailing exactly what your repository does, who it's meant for, and a screenshot of how it looks when completed. A permanently hosted demo link, like a vercel link for example, of what the template looks like when completed, is highly recommended.

#### Restrictions

Any language or platform can be added here - it's not just limited to sites. No NSFW or anything crazy is allowed of course - basically be cool. Anyone found to be abusing the system will be barred from further submissions.

## How to create and test your golaunch.yaml

A valid golaunch.yaml file is necessary in order for the site to know how your template works. It must be commited to the top level of your repo.

[Here's an example of a valid golaunch.yaml file](https://github.com/GoLaunch-dev/saas-waitlist-landingpage/blob/main/golaunch.yaml)

You can test yours on [the custom test page](https://golaunch.dev/custom)

A golaunch.yaml file is split into the following sections:

### metadata

Basically some meta information about the repo that'll be displayed on the template selection screen.

`template_name`: Your template's name, 10-35 characters

`template_demo_url`: A permanent demo url that the user can click on to see how your template looks and functions

`template_description`: A simple description, 25-100 characters long

`template_github_owner`: a link to your github user profile

`tags`: a list of technologies that allow the user to more easily identify what your template does. 4-8 tags works best

### fields

The fields the user will fill out when creating a repo with your template.

`label`: the name of the field, displayed to the user

`type`: the variable type, currently we support `string` and `png`

`description`: the description of your field, seen by the user

`codeId`: an id used internally to match, must be unique across fields

`codeDefined`: the string that our engine will REPLACE in your repo with the user's value. For example, all instances of {{name}} in your repo will be replaced by whatever the user enters into the form on golaunch. Only applicable to type `string`

`defaultValue`: the default value for a string

`required`: if the field is required

`aiGenable`: can the user use GoLaunch's AI to generate this field

`paths`: an array of path locations for type `png` to be saved. i.e if you allow the user to upload an image, all the paths you want it to be saved to

### ignore

ignore:

- golaunch.yaml

The `ignore` object takes a list of file/folder pathnames that will be ignored when our engine goes through and replaces files. By default, the following paths are ignored without any need to add them on your end:

```
const ignoredFiles: string[] = [
  '.DS_Store',
  '.env',
  '.idea/',
  'node_modules/',
  'dist/',
  'build/',
  'coverage/',
  '*.log',
  '*.tmp',
  '*.swp',
  '*.bak',
  '*.cache',
  '*.db',
  '*.sqlite',
  'golaunch.yaml',
  'package.json',
  'package-lock.json',
  'yarn.lock',
  'tsconfig.json',
  'jest.config.js',
  'webpack.config.js',
  'babel.config.js',
  'postcss.config.js',
  'rollup.config.js',
  'vite.config.js',
  'pnpm-lock.yaml',
  'yarn-error.log',
  'npm-debug.log',
  '.git/',
  '.vscode/',
  '.npm/',
  '.yarn/',
  '.pnp.js',
  '.eslintcache',
  '.prettierignore',
  '.prettierrc',
  '.editorconfig',
  '.gitignore',
  '.gitattributes',
  '.npmignore',
  '.nvmrc',
  '.env.example',
  '.env.local',
  '.env.development',
  '.env.test',
  '.env.production',
  'README.md',
  'LICENSE',
  'CHANGELOG.md',
  'CONTRIBUTING.md',
  'CODE_OF_CONDUCT.md',
  'SECURITY.md'
]
```

### Post install instructions

If you have any specific actions the user should take after setting the repository is cloned (i.e setting up environment variables, running a command, creating tables in their database, signing up for a service your code integrates with, etc), you can add a specific `setup.md` to the root of your project, who's markdown contents will be displayed to the user after the repo is cloned. Alternatively, if no `setup.md` is found, it will by default display the `README.md` file at the root of your template.

# How to submit

Once you've verified and tested your template out at [the custom test page](https://golaunch.dev/custom) you can create a merge request on this repo detailing exactly what your repository does, who it's meant for, and a screenshot of how it looks when completed.

# Restrictions

Templates for any language / framework / platform can be added here - it's not just limited to sites. No NSFW or anything crazy is allowed of course - basically be cool. Anyone found to be abusing the system will be barred from further submissions.
