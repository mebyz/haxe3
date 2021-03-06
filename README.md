![Haxe logo](http://haxe.org/img/haxe-logo.svg)
# [Haxe 3 - The Cross-Platform Toolkit (a fork from David Mouton's damoebius/haxe-npm) ](http://haxe.org)

haxe
========

Installs [Haxe](http://haxe.org) using [NPM](https://www.npmjs.com/)

## Features

* Global or per-project, sandboxed, standard Haxe installation
* No dependency to Neko/libneko
* Available on Ubuntu/Linux/Windows/OSX

## Installation

If you have the node package manager, npm, installed:

```shell
npm install -g haxe
```

Leave off the `-g` if you don't wish to install globally.

## Getting Started

Execute a script:

```shell
haxe --help
```

Compile a script:
Developing Javascript code is really easy with Haxe. Let's see our first HelloWorld example :

```shell
class Test {
    static function main() {
        trace("Hello World !");
    }
}
```
Put this class into a file named Test.hx and create the file compile.hxml in the same directory with the following content :
```shell
-js test.js
-main Test
```
To compile, run the command : 

```shell
haxe compile.hxml
```

## Using package.json

Create a simple file package.json at the root of your project and add dependencies to haxe and haxelibs

```shell
{
  "name": "BikeWar",
  "description": "Code Of War 3",
  "keywords": [
    "contest",
    "haxe"
  ],
  "author": "David Mouton",
  "version": "0.8.1",
  "license": "MIT",
  "engines": {
    "node": ">=0.8.0"
  },
  "main": "",
  "preferGlobal": false,
  "homepage": "http://www.codeofwar.net",
  "bugs": "https://github.com/damoebius/BikeWar/issues",
  "repository": {
    "type": "git",
    "url": "git://github.com/damoebius/BikeWar.git"
  },
  "dependencies": {
     "haxe" : "3.2.1",
     "taminahx" : ">=0.1.0",
     "mconsole-npm" : ">=1.6.1",
     "msignal" : ">=1.2.3"
  }
}
```

### Version

See [Haxe Download list](http://haxe.org/download/list/).
Please notice the directory name in the archive must match.

run the npm command line to configure your project
```shell
npm install
```

## Using Ant build.xml

Target exemple :
```shell
<target name="compile-ia">
    <mkdir dir="${output.js}"/>

    <exec executable="node" failonerror="true" dir="Player">
        <arg line="node_modules\haxe\bin\haxe-cli.js"/>
        <arg line="-cp src -js ${output.js}/MyIA.js -main MyIA -debug"/>
        <arg line="-lib taminahx"/>
    </exec>
</target>
```


## -lib 
-lib will use a library declared in your npm dependencies


For documentation, usage, and examples, see: http://haxe.org/

haxelib
========
Haxelib support is coming soon


