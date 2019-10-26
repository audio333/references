link: https://raw.githubusercontent.com/joshbedo/npm-cheatsheet/master/README.md


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