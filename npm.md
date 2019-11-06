link: https://gist.githubusercontent.com/bradtraversy/09177818de0f43a6e74e2cd05d1fe596/raw/26f908bfad766f7c5156de7d6d4d1c0a510e1a1a/npmcrashcourse.txt

### GET VERSION
```shell
npm -v (or --version)
```

### GET HELP
```shell
npm help
npm
```

### CREATE PACKAGE.JSON
```shell
npm init
npm init -y (or --yes)
```

### SET DEFAULTS
```shell
npm config set init-author-name "YOUR NAME"
npm set init-license "MIT"
```

### GET DEFAULTS
```shell
npm config get init-author-name
npm get init-license
```

### REMOVE DEFAULTS
```shell
npm config delete init-author-name
npm delete init-license
```

### INSTALLING LOCAL PACKAGES
```shell
npm install lodash --save (or npm install --save lodash)
npm install moment --save
npm install gulp gulp-sass --save-dev
```

### MOVE TO ANOTHER FOLDER
```shell
npm install
npm install --production
```

### REMOVING MODULES
```shell
npm uninstall gulp-sass --save-dev
npm remove gulp --save-dev
```

### INSTALL CERTAIN VERSIONS
```shell
npm install lodash@4.17.3 --save
```

### UPDATE
```shell
npm update lodash --save
```

### INSTALL GLOBAL MODULE
```shell
npm install -g nodemon
npm install -g live-server
```

### RUN NODEMON
```shell
nodemon
```

### FIND ROOT FOLDER
```shell
npm root -g
```

### REMOVE GLOBAL PACKAGES
```shell
npm remove -g nodemon
```

### LISTING PACKAGES
```shell
npm list
npm list --depth 0
npm list --depth 1
```

### INSTALL LIVE-SERVER LOCALLY
```shell
npm install live-server --save-dev
```

### NPM SCRIPT
```json
"scripts": {
    "start": "node index.js",
    "dev": "live-server"
  },
```

---
link: https://raw.githubusercontent.com/joshbedo/npm-cheatsheet/master/README.md

## Contents
1. [Commands](#commands)
2. [Packages](#packages)

## Commands

* quick help on <cmd>

   `npm <cmd> -h`
* display full usage info

   `npm -l`
* add a registry user account

   `npm adduser`
* display npm bin folder

   `npm bin`
* bugs for a package in a web browser maybe

   `npm bugs <pkgname>`
* build a package (should not be called directly)

   `npm build <package-folder>`
* manipulates packages cache

   `npm cache [add|ls|clean] <tarball|folder>`
* manage the npm configuration files

   `npm config [set|get|delete|list|edit] <key> <value>`
* reduce duplication

   `npm dedupe [package names...]  --tag`
* deprecate a version of a package (must be the package owner)

   `npm decrecate <name>[@<version>] <message>`
* docs for a package in a web browser maybe

   `npm docs [<pkg-name> [<pkg-name> ...]]`
* edit an installed package (default EDITOR set to "vi")

   `npm edit <name>[@<version>]`
* browse an installed package

   `npm explore <name>[@<version>] [ -- <cmd>]`
* commonly asked questions

   `npm faq`
* search npm help documentation (rarely necessary to call directly)

   `npm help-search <some search terms>`
* get help on npm

   `npm help <topic> <some search terms>`
* interactively create a package.json file

   `npm init`
* install a package (optional flags: --save, --save-dev, --save-optional, --save-exact)

   `npm install <folder|name@<tag|version>|tarball>`
* symlink a package folder

   `npm link <pkgname>`
* list installed packages (as well as their dependencies)

   `npm ls <pkg>`
* check for outdated packages

   `npm outdated [<name> [<name> ...]]`
* manage package owners

   `npm owner [ls|add|rm] <pkg-name> <user>`
* create a tarball from a package

   `npm pack [<pkg> [<pkg> ...]]`
* display prefix

   `npm prefix`
* remove extraneous packages

   `npm prune [<name> [<name ...]] --production`
* publish a package

   `npm publish <tarball|folder> [--tag <tag>]`
* rebuild a package

   `npm rebuild [<name > [<name> ...]]`
* open package repository in the browser

   `npm repo <pkgname>`
* start a package

   `npm restart <name>`
* remove a package

   `npm rm <name>`
* display npm root

   `npm root`
* run arbitrary package scripts

   `npm run [<pkg>] [command]`
* search for packages

   `npm search [search terms ...] [--long]`
* lock down dependency versions

   `npm shrinkwrap`
* mark your favorite packages

   `npm star <pkgname> [<pkg>, ...]`
* view packages marked as favorites

   `npm stars [username]`
* start a package

   `npm start <name>`
* stop a package

   `npm stop <name>`
* add a package as a git submodule

   `npm submodule <pkg>`
* tag a published version

   `npm tag <name>@<version>`
* test a package

   `npm test <name>`
* remove a package from the registry

   `npm unpublish <name>[@<version>]`
* Unfavorite specified p

   `npm unstar <pkgname> [<pkg>, ...]`
* update a package

   `npm update [-g] [<name> [<name> ...]]`
* bump a package version

   `npm version [<newversion> | major | minor | patch]`
* view registry info

   `npm view <name>[@<version>] [<field<[.<subfield>] ...]`
* display npm username

   `npm whoami`


## Packages
* axios
* bootstrap
* bootstrap-sass
* browser sync
* font-awesome
* jquery
* laravel-mix
* gulp
   * gulp-sass
   * gulp-notify
   * gulp-plumber
   * gulp-concat
   * gulp-imagemin
   * gulp-notify
   * gulp-sourcemaps
   * gulp-uglify
   * gulp-uglifycss
* node-sass
* sass
* sass-loader
* vue