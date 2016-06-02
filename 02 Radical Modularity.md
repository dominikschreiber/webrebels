# Radical Modularity
Aria Stewart (@aredridel)

- definition of a module:
	- *basic definition:* bit of software with a *defined* interface to the rest of the system
	- *npm definition:* basic definition + a name
- defining a module: intentional act (-> name, interface, ...)
- publishing a module: intentional act (-> version numbers, dependencies, ...)
- two open source movements:
	- laws, copyright, licenses
	- sharing, extending, building
- modules as art (e.g. a module depending on every other module, a module taking the name of a namespace away)
- small modules > big modules (as big modules are only a bunch of small modules that are not clearly defined)
- modularize everything
	- css ([dr-frankenstyle](https://www.npmjs.com/package/dr-frankenstyle), [atomify-css](https://www.npmjs.com/package/atomify-css))
	- svg (`x-link`)
	- templates & helpers (e.g. handlebars: `{{fromPackage @hugo/templates/willi.tpl .}}`)
	- React (`require`)
	- i18n
	- websites
	- licenses
	- JSON schemas
	- legal terms
- how to make modularity
	- `resolve.sync('@hugo/assets/willi.svg')`
	- resolve paths by main entry points (different for technologies -- e.g. `index.js` for Javascript, `asset.svg` for svg, ...)
- simple interfaces win (e.g. unix: everything is a file)