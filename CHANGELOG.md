# CHANGELOG

## v1.3.2 (Oct 3, 2016)
* Support for [precinct](https://github.com/dependents/node-precinct) detective option `es6.mixedImports`.

## v1.3.1 (Oct 1, 2016)
* Allow to pass options to [dependency-tree](https://github.com/dependents/node-dependency-tree) detectives (Thanks to [Fabio Crisci](https://github.com/piuccio)).

## v1.3.0 (Sep 6, 2016)
* Big performance boost when running on large codebases.

## v1.2.0 (Sep 1, 2016)
* Added option `--stdin` to be used for piping a predefined tree.

## v1.1.0 (Aug 23, 2016)
* Support for setting custom GraphViz options with config `graphVizOptions`.

## v1.0.0 (Aug 19, 2016)

After 4 years of adding features/fixes it started to be hard to maintain the project and fix some outstanding issues due to how madge was designed to work.

So I decided it was high time for version 1.0 to be released and take the opportunity to do a major rewrite and reduce the size and responsibility of the project and delegate some work to [external libraries](https://github.com/mrjoelkemp/node-dependency-tree). This introduced many breaking changes. Here's the most important ones.

**Added:**

* Automatic module type detection thanks to [precinct](https://github.com/mrjoelkemp/node-precinct)
* Determine image format based on file extension (SVG support)
* Reading [config](README.md#configuration) from `.madgerc` (replaces `--config`)
* Option `--webpack-config` for supporting aliased module paths
* Option `--debug` for turning on debug output

**Changed:**

* Renamed many of the settings in the [config](README.md#configuration)
* Option `--json` should now be used instead of `--output json`
* The generation of the dependency tree is now delegated to the external module [dependency-tree](https://github.com/mrjoelkemp/node-dependency-tree)
* Recurse into child dependencies to get a complete dependency tree of a file
* NPM installed dependencies are now excluded by default
* Node.js core modules are now excluded
* The [API](README.md#api) is now using promises

**Removed:**

* Option `--format` since the format is now detected automatically from the file content
* Option `--optimized` and `--main-require-module` since we no longer support RequireJS builds (r.js)
* Option `--read`
* Option `--find-nested-dependencies`
* Option `--paths`
* Option `--config`
* Option `--output`
* Option `--break-on-error`
* CoffeeScript support
* Event callbacks `onParseFile` and `onAddModule`
* NPM shrinkwrap no longer used

## v0.6.0 (July 06, 2016)
* Refactored Madge to use ES6 and now requires Node.js 4 to run.

## v0.5.5 (July 03, 2016)
* Add note about Graphviz and Windows in README.
* Fix matching absolute path in Windows (Thanks to nadejdashed).
* Support for ES6 re-export syntax (Thanks to Oli Lalonde).
* Support files with ES6 (Thanks to Joel Kemp).
* Improve readme circular return object (Thanks to Way Of The Future).

## v0.5.4 (June 13, 2016)
* Improved JSX and ES7 support (Thanks to Joel Kemp).

## v0.5.3 (November 25, 2015)
* Correct regex on CommonJS parser to detect a core module (Thanks to Guillaume Gomez).

## v0.5.2 (October 16, 2015)
* Updated dependency resolve to latest version.

## v0.5.1 (October 15, 2015)
* Updated dependencies to newer versions (Thanks to Martin Kapp).

## v0.5.0 (April 2, 2015)
* Added support for ES6 modules (Thanks to Marc Laval).
* Added support for setting custom file extension name (Thanks to Marc Laval).

## v0.4.1 (December 19, 2014)
* Fixed issues with absolute paths for modules IDs in Windows (all tests should now pass on Windows too).

## v0.4.0 (December 19, 2014)
* Add support for JSX (React) and additional module paths (Thanks to Ben Lowery).
* Fix for detecting presence of AMD or CommonJS modules (Thanks to Aaron Russ).
* Now resolves the module IDs from the RequireJS paths-config properly (Thanks to russaa).
* Added support for option findNestedDependencies to find nested dependencies in AMD modules.

## v0.3.5 (Septemper 22, 2014)
* Fix issue with number of graph node lines increased with each render (Thanks to Colin H. Fredericks).

## v0.3.4 (Septemper 04, 2014)
* Correctly detect circular dependencies when using path aliases in RequireJS config (Thanks to Nicolas Ramz).

## v0.3.3 (July 11, 2014)
* Fixed bug with relative paths in AMD not handled properly when checking for cyclic dependencies.

## v0.3.2 (June 25, 2014)
* Handle anonymous require() as entry in the RequireJS optimized file (Thanks to Benjamin Horsleben).

## v0.3.1 (June 03, 2014)
* Apply exclude to RequireJS shim dependencies (Thanks to Michael White).

## v0.3.0 (May 25, 2014)
* Added support for onParseFile and onAddModule options (Thanks to Brandon Selway).
* Added JSON output option (Thanks to Drew Foehn).
* Fix for optimized files including dependency information for excluded modules (Thanks to Drew Foehn). Fixes [issue](https://github.com/pahen/madge/issues/26).

## v0.2.0 (April 17, 2014)
* Added support for including shim dependencies found in RequiredJS config (specify with option -R).

## v0.1.9 (February 17, 2014)
* Ensure forward slashes are used in modules paths (Windows).

## v0.1.8 (January 27, 2014)
* Added support for reading AMD dependencies from a r.js optimized file by using option -O.

## v0.1.7 (September 20, 2013)
* Added missing fontsize option when generating images.

## v0.1.6 (September 04, 2013)
* AMD plugins are now ignored as dependencies. Fixes [issue](https://github.com/pahen/grunt-madge/issues/1).

## v0.1.5 (September 04, 2013)
* Fixed Windows [issue](https://github.com/pahen/madge/issues/17) when reading from standard input with --read.

## v0.1.4 (January 10, 2013)
* Switched library for walking directory tree which should solve issues on [Windows](https://github.com/pahen/madge/issues/8).

## v0.1.3 (December 28, 2012)
* Added proper exit code when running "madge --circular" so it can be used in build scripts.

## v0.1.2 (November 15, 2012)
* Relative AMD module identifiers (if the first term is "." or "..") are now resolved.

## v0.1.1 (September 3, 2012)
* Tweaked circular dependency path output.

## v0.1.0 (September 3, 2012)
* Complete path in circular dependencies is now printed (and marked as red in image graphs).

## v0.0.5 (August 8, 2012)
* Added support for CoffeeScript. Files with extension .coffee will automatically be compiled on-the-fly.

## v0.0.4 (August 17, 2012)
* Fixed dependency issues with Node.js v0.8.

## v0.0.3 (July 01, 2012)
* Added support for Node.js v0.8 and dropped support for lower versions.

## v0.0.2 (May 21, 2012)
* Added ability to read config file and customize colors.

## v0.0.1 (May 20, 2012)
* Initial release.