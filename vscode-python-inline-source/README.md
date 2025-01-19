# Python Inline Source Syntax Highlighting

> The original [Python Inline Source](https://github.com/samwillis/python-inline-source) by Sam Willis
> is no longer maintained. Please raise your issues and questions in
> [jurooravec/python-inline-source-2](https://github.com/jurooravec/python-inline-source-2).
>
> The PyPI package and VSCode extension have also been migrated:
> - PyPI: [sourcetypes](https://pypi.org/project/sourcetypes/) -> [sourcetypes2](https://pypi.org/project/sourcetypes2/)
> - VSCode: [samwillis.python-inline-source](https://marketplace.visualstudio.com/items?itemName=samwillis.python-inline-source) -> [jurooravec.python-inline-source-2](https://marketplace.visualstudio.com/items?itemName=jurooravec.python-inline-source-2)
>
> This fork is based on [v0.0.4](https://github.com/samwillis/python-inline-source/releases/tag/v0.0.4).

VS Code plugin to add syntax highlight to multi line Python strings using type 
annotations. Supports `html`, `css`, `javascript`, `typescript`, `sql`, `graphql`, 
multiple *css extension languages*, *template languages* and many more, 
[see below](#supported-languages) for a full list.

## Installation

Install `python-inline-source-2` from extensions (`ctrl + shift + x` or `cmd + shift + x` 
on mac).

Also available on [marketplace.visualstudio.com](https://marketplace.visualstudio.com/items?itemName=jurooravec.python-inline-source-2)

## Example

![Example](docs/examples.png)

## Usage

Use a type decoration named for language that you are using, the simplest for of this is
to do something like this:

```
html = str  # Create an alias of the str type named for the language you are using

my_html_string: html = """
  <h1>Some HTML</h1>
"""
```

In order to aid with the type decorations the `sourcetypes` package can be 
installed (`pip install sourcetypes`) which allows this for all supported 
languages:

```
import sourcetypes

my_html_string: sourcetypes.html = """
  <h1>Some HTML</h1>
"""
```

The `sourcetypes` package uses [typing.Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)
to annotate the `str` type with the language used. You can use 
[typing.get_type_hints](https://docs.python.org/3/library/typing.html#typing.get_type_hints) 
at runtime to determine the language that a string has been annotated with.

## Supported Languages

- `markdown` (aliased as `md`)
- `html`
- `django_html` (aliased as `django`)
- `django_txt`
- `jinja`
- `jinja_html`
- `css` (aliased as `style`, and `styles`)
- `scss`
- `less`
- `sass`
- `stylus`
- `javascript` (aliased as `js`)
- `jsx` (aliased as `javascriptreact`, and `react`)
- `typescript` (aliased as `ts`)
- `tsx` (aliased as `typescriptreact`)
- `coffeescript` (aliased as `coffee`)
- `sql`
- `json`
- `yaml`
- `graphql`
- `xml`
- `python`
- `glsl`

## Requirements

- At least Visual Studio Code v1.64.0 recommended, not tested on older versions.

## Release Notes

### [0.0.4] - 2024-10-17
- Make the space between `:` optional. [#3](https://github.com/samwillis/python-inline-source/issues/3).

### [0.0.3] - 2024-10-17
- Forked from v0.0.2

## Dev notes

See https://code.visualstudio.com/api/working-with-extensions/publishing-extension

```sh
npm install -g @vscode/vsce
```

Packaging:

```sh
vsce package
```

Publishing:

```sh
vsce publish
```
