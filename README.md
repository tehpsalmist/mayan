# mayan

A port of [maya](https://github.com/ZengineHQ/maya) in NodeJS

[![Build Status](https://drone.appsrv.com/api/badges/Wizehive/mayan/status.svg)](https://drone.appsrv.com/Wizehive/mayan)

## Install

```
npm install -g git+ssh://git@github.com/WizeHive/mayan
```

## Using

```
$ mayan

mayan <command>

Commands:
  mayan build [plugin]    Build plugin
  mayan deploy [plugin]   Deploy plugin
  mayan publish [plugin]  Publish plugin

Options:
  --version      Show version number                                   [boolean]
  --env          Environment name
  --config       Path to JSON config file
  --help         Show help                                             [boolean]

```

## Differences from maya

mayan strives to be 100% backwards compatible with original maya but also adds some additional new features:

- Write frontend plugins using ES6 features such as arrow functions, let/const, destructuring, rest/spread, etc
- Write frontend plugin styles using SCSS
- You can also keep on using vanilla js and css if that's your thing
- Support for frontend plugin modules directly in the main plugin package.json as regular dependencies (the old `src` dir approach also works)
- Follows symlinks for @zenginehq modules for a great local development experience
- Ability to `--skip-build` when deploying and publishing and `--skip-deploy` when publishing
- Minifies CSS, JS and HTML when `prod` or `production` environment used
- Supports `maya-pre-build` and `maya-post-build` package.json scripts for both backend services and frontend plugins (the old `maya-build` in backend services still functions as post build)
- The maya build artifact location and folder structure has changed

## Contributing


### Fork

```
git clone git@github.com:Wizehive/mayan.git
```

### Install dependencies

```
npm install
```

### Test and lint

```
npm test
npm run eslint
```

### Install binary locally

```
npm link
```

### Adding new commands

Follow this [approach/strategy](https://github.com/yargs/yargs/blob/master/docs/advanced.md#example-command-hierarchy-using-commanddir) to organize commands
