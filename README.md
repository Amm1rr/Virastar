# Virastar (ویراستار)
Virastar is a Persian text cleaner.

A javascript port of [aziz/virastar](https://github.com/aziz/virastar)

see live [demo](https://virastar.brothersincode.ir)

[![Build Status](https://img.shields.io/travis/brothersincode/virastar/master.svg?style=flat-square)](https://travis-ci.org/brothersincode/virastar)
[![Dependency Status](https://img.shields.io/david/brothersincode/virastar.svg?style=flat-square)](https://david-dm.org/brothersincode/virastar)
[![NPM version](https://img.shields.io/npm/v/virastar.svg?style=flat-square)](https://www.npmjs.com/package/virastar)
[![GitHub issues](https://img.shields.io/github/issues/brothersincode/virastar.svg?style=flat-square)](https://github.com/brothersincode/virastar/issues)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://raw.githubusercontent.com/brothersincode/virastar/master/LICENSE)
[![js-semistandard-style](https://img.shields.io/badge/code%20style-semistandard-brightgreen.svg?style=flat-square)](https://github.com/Flet/semistandard)

## Install
``` bash
npm install virastar
```

## Usage
```js
var Virastar = require('virastar');
var virastar = new Virastar();

virastar.cleanup("فارسي را كمی درست تر می نويسيم");
// Outputs: "فارسی را کمی درست‌تر می‌نویسیم"
```

### Browser
```html
<script src="lib/virastar.js"></script>
<script>
  var virastar = new Virastar();
  alert(virastar.cleanup("فارسي را كمی درست تر می نويسيم"));
</script>
```

#### Virastar([text] [,options])

##### text
Type: `string`

String of Persian source to be cleaned.

##### options
Type: `object`

```js
Virastar("سلام 123" ,{"fix_english_numbers":false});
// Outputs:"سلام 123"
```

## Options and Specifications
Virastar comes with a list of options to control its behavior.

_all options are **enabled** by default._

* `normalize_eol`
	- replace Windows end of lines with Unix EOL (`\n`)


* `decode_htmlentities`
	- converts all HTML characterSets into original characters


* `fix_dashes`
	- replace double dash to ndash and triple dash to mdash


* `fix_three_dots`
	- replace three dots with ellipsis


* `normalize_ellipsis`
	- replace more than one ellipsis with one


* `fix_english_quotes_pairs`
	- replace English quotes pairs (`“”`) with their Persian equivalent (`«»`)


* `fix_english_quotes`
	- replace English quotes, commas and semicolons with their Persian equivalent


* `fix_hamzeh`
	- convert `ه ی` to `هٔ`
	- convert `ه ء` to `هٔ`


* `cleanup_rlm`
	- converting Right-to-left marks followed by Persian characters to zero-width non-joiners (ZWNJ)


* `cleanup_zwnj`
	- remove more than one zwnj chars
	- remove unnecessary zwnj chars that are succeeded/preceded by a space
	- clean zwnj chars after Persian characters that don't conncet to the next letter
	- clean zwnj chars before English characters
	- clean zwnj chars after and before punctuation
	- clean zwnj chars before diacritic characters


* `fix_arabic_numbers`
	- replace Arabic numbers with their Persian equivalent


* `fix_english_numbers`
	- replace English numbers with their Persian equivalent
	- should not replace English numbers in English phrases


* `skip_markdown_ordered_lists_numbers_conversion`
	- skip converting English numbers of ordered lists in markdown


* `fix_misc_non_persian_chars`
	- replace Arabic kaf with its Persian equivalent
	- replace Arabic/Urdu/Pushtu/Uyghur Yeh with its Persian equivalent
	- replace Kurdish He with its Persian equivalent


* `fix_punctuations`
	- replace `%`, `,`, `;` with its Persian equivalent


* `fix_question_mark`
	- replace question marks with its Persian equivalent


* `fix_perfix_spacing`
	- put zwnj between word and prefix:
		- `mi*`, `nemi*`, `bi*`


* `fix_suffix_spacing`
	- put zwnj between word and suffix:
		- `*am`, `*at`, `*ash`, `*ei`, `*eid`, `*eem`, `*and`
		- `*ha`, `*haye`
		- `*tar`, `*tari`, `*tarin`
		- `*hayee`, `*hayam`, `*hayat`, `*hayash`, `*hayetan`, `*hayeman`, `*hayeshan`


* `fix_spacing_for_braces_and_quotes`
	- fix spacing for `()` `[]` `{}`  `“”` `«»` (one space outside, no space inside)
	- correct `:;,.?!` spacing (one space after and no space before)


* `cleanup_spacing`
	- replace more than one space with just a single one
	- clean spaces before diacritic characters


* `cleanup_line_breaks`
	- remove more than **two** contiguous line breaks


* `cleanup_begin_and_end`
	- remove spaces, tabs, and new lines from the beginning and end of text

#### aggressive editing
* `aggresive`
	- enable/disable aggressive editing


* `cleanup_extra_marks`
	- replace more than one `!` or `?` mark with just one


* `kashidas_as_parenthetic`
	- replace kashidas to ndash in parenthetic


* `cleanup_kashidas`
	- remove all kashidas

#### extras
* `preserve_HTML`
	- preserve all HTML tags


* `preserve_comments`
	- preserve all HTML comments


* `preserve_entities`
	- preserve all HTML entities


* `preserve_URIs`
	- preserve all URI links in the text


* `preserve_brackets`
	- preserve strings inside square brackets (`[]`)


* `preserve_braces`
	- preserve strings inside curly braces (`{}`)


* `preserve_nbsps`
	- preserve all no-break spaces

## License

This software is licensed under the MIT License. [View the license](LICENSE).
