# Python Inline Source 2: Syntax Highlighting Using Type Annotations

> The original [Python Inline Source](https://github.com/samwillis/python-inline-source) by Sam Willis
> is no longer maintained. Please raise your issues and questions in this repo.
>
> The PyPI package and VSCode extension have also been migrated:
> - PyPI: [sourcetypes](https://pypi.org/project/sourcetypes/) -> [sourcetypes2](https://pypi.org/project/sourcetypes2/)
> - VSCode: [samwillis.python-inline-source](https://marketplace.visualstudio.com/items?itemName=samwillis.python-inline-source) -> [jurooravec.python-inline-source-2](https://marketplace.visualstudio.com/items?itemName=jurooravec.python-inline-source-2)
>
> This fork is based on [v0.0.4](https://github.com/samwillis/python-inline-source/releases/tag/v0.0.4).

This project enables inline syntax highligting of strings in python source files for 
multiple languages using type annotations.

Supports `html`, `css`, `javascript`, `typescript`, `sql`, `graphql`, 
multiple *css extension languages*, *template languages* and many more, 
[see below](#supported-languages) for a full list.

Uses [typing.Annotated](https://docs.python.org/3/library/typing.html#typing.Annotated)
to annotate the `str` type with the language used. You can use 
[typing.get_type_hints](https://docs.python.org/3/library/typing.html#typing.get_type_hints) 
at runtime to determine the language that a string has been annotated with.

- [sourcetypes](https://github.com/jurooravec/python-inline-source-2/tree/main/sourcetypes) Python Types Package.
- [vscode-python-inline-source](https://github.com/jurooravec/python-inline-source-2/tree/main/vscode-python-inline-source) VS Code Plugin.

## Installation

### Python package:

```
pip install sourcetypes2
```

### VS Code plugin:

Install `python-inline-source-2` from extensions (`ctrl + shift + x` or `cmd + shift + x` 
on mac).

Also available on [marketplace.visualstudio.com](https://marketplace.visualstudio.com/items?itemName=jurooravec.python-inline-source-2)

## Example

[![Example](sourcetypes/docs/examples.png)](sourcetypes/docs/examples.py)

## Usage

Use a type decoration named for language that you are using:

```
import sourcetypes

my_html_string: sourcetypes.html = """
  <h1>Some HTML</h1>
"""
```

or:

```
from sourcetypes import html

my_html_string: html = """
  <h1>Some HTML</h1>
"""
```

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
