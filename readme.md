# find-up [![Build Status: Linux and macOS](https://travis-ci.org/sindresorhus/find-up.svg?branch=master)](https://travis-ci.org/sindresorhus/find-up) [![Build Status: Windows](https://ci.appveyor.com/api/projects/status/l0cyjmvh5lq72vq2/branch/master?svg=true)](https://ci.appveyor.com/project/sindresorhus/find-up/branch/master) [![find-up Dev Token](https://badge.devtoken.rocks/find-up)](https://devtoken.rocks/package/find-up)

> Find a file or directory by walking up parent directories

---

<div align="center">
	<b>
		<a href="https://tidelift.com/subscription/pkg/npm-find-up?utm_source=npm-find-up&utm_medium=referral&utm_campaign=readme">Get professional support for 'find-up' with a Tidelift subscription</a>
	</b>
	<br>
	<sub>
		Tidelift helps make open source sustainable for maintainers while giving companies<br>assurances about security, maintenance, and licensing for their dependencies.
	</sub>
</div>

---

## Install

```
$ npm install find-up
```


## Usage

```
/
└── Users
		└── sindresorhus
				├── unicorn.png
				└── foo
						└── bar
								├── baz
								└── example.js
```

`example.js`

```js
const findUp = require('find-up');

(async () => {
	console.log(await findUp('unicorn.png'));
	//=> '/Users/sindresorhus/unicorn.png'

	console.log(await findUp(['rainbow.png', 'unicorn.png']));
	//=> '/Users/sindresorhus/unicorn.png'
})();
```


## API

### findUp(filename, [options])

Returns a `Promise` for either the filepath or `null` if it couldn't be found.

### findUp([filenameA, filenameB], [options])

Returns a `Promise` for either the first filepath found (by respecting the order) or `null` if none could be found.

### findUp.sync(filename, [options])

Returns a filepath or `null`.

### findUp.sync([filenameA, filenameB], [options])

Returns the first filepath found (by respecting the order) or `null`.

#### filename

Type: `string`

Filename of the file to find.

#### options

Type: `Object`

##### cwd

Type: `string`<br>
Default: `process.cwd()`

Directory to start from.


## Related

- [find-up-cli](https://github.com/sindresorhus/find-up-cli) - CLI for this module
- [pkg-up](https://github.com/sindresorhus/pkg-up) - Find the closest package.json file
- [pkg-dir](https://github.com/sindresorhus/pkg-dir) - Find the root directory of an npm package
- [resolve-from](https://github.com/sindresorhus/resolve-from) - Resolve the path of a module like `require.resolve()` but from a given path


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
