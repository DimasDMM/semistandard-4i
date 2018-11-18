# JS Semistandard 4I Style
[![npm][npm-image]][npm-url]
[![downloads][downloads-image]][downloads-url]

[npm-image]: https://img.shields.io/npm/v/semistandard-4i.svg?style=flat-square
[npm-url]: https://npmjs.org/package/semistandard-4i
[downloads-image]: https://img.shields.io/npm/dm/semistandard-4i.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/semistandard-4i

### One Semicolon for the Dark Lord on his dark throne

All the goodness of [JS Standard Style](https://github.com/standard/standard) with semicolons and 4 spaces indentation.

## Install

```bash
npm install semistandard-4i
```

## Rules

Importantly:

- **semicolons**
- **4 spaces indentation**
- Check [JS Standard Style](https://github.com/standard/standard) for the rest of the rules.

## Badge

Use this in one of your projects? Include one of these badges in your readme to
let people know that your code is using this code style.

[![js-semistandard-4i-style](https://img.shields.io/badge/JS%20Code%20Style-Semistandard%204I-brightgreen.svg)](https://github.com/DimasDMM/semistandard-4i)

```markdown
[![js-semistandard-4i-style](https://img.shields.io/badge/JS%20Code%20Style-Semistandard%204I-brightgreen.svg)](https://github.com/DimasDMM/semistandard-4i)
```

## Usage

The easiest way to use this code style to check your code is to install it
globally as a Node command line program. To do so, simply run the following command in
your terminal (flag `-g` installs `semistandard-4i` globally on your system, omit it if you want
to install in the current working directory):

```bash
npm install semistandard-4i -g
```

After you've done that you should be able to use the `semistandard-4i` program. The simplest use
case would be checking the style of all JavaScript files in the current working directory:

```
$ semistandard-4i
Error: Use JS Semistandard 4I Style
  lib/torrent.js:950:11: Expected '===' and instead saw '=='.
```

### What you might do if you're clever

1. Add it to `package.json`

```json
{
  "name": "my-cool-package",
  "devDependencies": {
    "semistandard-4i": "*"
  },
  "scripts": {
    "test": "semistandard-4i && node file-with-this-style.js"
  }
}
```

2. Check style automatically when you run `npm test`

```
$ npm test
Error: Code style check failed:
  lib/torrent.js:950:11: Expected '===' and instead saw '=='.
```

3. Never give style feedback on a pull request again! (unless it's about semicolons)

### Custom Parser
To use a custom parser, install it from npm (example: `npm install
babel-eslint`) and add this to your package.json:

```json
{
  "semistandard-4i": {
    "parser": "babel-eslint"
  }
}
```

### [Vim](http://www.vim.org/)

Install **[Syntastic][vim-1]** and add these lines to `.vimrc`:

```vim
let g:syntastic_javascript_checkers=['standard']
let g:syntastic_javascript_standard_exec = 'semistandard-4i'
```

For automatic formatting on save, add these two lines to `.vimrc`:

```vim
autocmd bufwritepost *.js silent !semistandard-4i % --fix
set autoread
```

[vim-1]: https://github.com/scrooloose/syntastic

### Ignoring files

Just like in `standard`, the paths `node_modules/**`, `*.min.js`, `bundle.js`, `coverage/**`, hidden files/folders
(beginning with `.`) and all patterns in a project's root `.gitignore` file are
automatically excluded when looking for `.js` files to check.

Sometimes you need to ignore additional folders or specific minfied files. To do that, add
a `semistandard-4i.ignore` property to `package.json`:

```json
"semistandard-4i": {
  "ignore": [
    "**/out/",
    "/lib/select2/",
    "/lib/ckeditor/",
    "tmp.js"
  ]
}
```

### Make it look `snazzy`
If you want prettier output, just install the [`snazzy`](https://github.com/feross/snazzy) package and pipe `semistandard-4i` to it:

```bash
$ semistandard --verbose | snazzy
```

### Future work

* Add tests with files following this code style.

### Useful links

* Original code style: [JS Standard Style](https://github.com/standard/standard).
* This repository is a fork of [Flet/semistandard](https://github.com/Flet/semistandard).

