# NODEJS

### Install

$ brew install node
$ brew upgrade node

#### Install the previous version

$ brew install node@8
$ brew link node@8

$ brew unlink node@8
$ brew uninstall node@8

### NPM

$ npm init
$ npm init --yes

$ npm install [packge name]
  (or npm i [package name])
$ npm install underscore
  (or $ npm i underscore)

Versioning
- SamVer: Major.Minor.Patch

^4.3.6 --> 4.x (the same Major) eg. 4.3.7, 4.4.0
~1.8.3 --> 1.8.x (the same Major.Minor) eg. 1.8.4
 2.1.5 --> 2.1.5 (the same Major.Minor.Patch)

$ npm list
$ npm list --depth=0

$ npm view mongoose dependencies
$ npm view mongoose versions
