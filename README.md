# MaTeXart

> A package with useful macros and environments for math papers.

## Description

This is a package created for math article authors. The functions mainly include two parts: lots of math commands, and macros helping defining math commands and environments. The main purpose is to automate the process of defining commands and environment, resulting in saving a lot of time for users.

## Install

1. Download the whole folder and copy it into the package folder of your $\LaTeX$.
2. Execute `texhash` to update the package list (sometimes require `sudo`)

## Options

| Option | Default | Description |
| --- | --- | --- |
| `disable-matdef` | No | Disable the `\matdef` macro |
| `enable-matdef` | Yes | Enable the `\matdef` macro |

### `disable-matdef`
Disable the `\matdef` macro. See also option [`enable-matdef`](#enable-matdef) and macro [`\matdef`](#matdef).
### `enable-matdef`

Enable the `\matdef` macro. See also option [`disable-matdef`](#disable-matdef) and macro [`\matdef`](#matdef).

## Macros

| Macro | Description |
| --- | --- |
| `\disablematdef` | Disable the `\matdef` macro |
| `\enablematdef` | Enable the `\matdef` macro |
| `\matdef` | Define macros with no parameter by `<control> -> <replacement>;` |

### `\disablematdef`

Disable the `\matdef` macro. See also option [`disable-matdef`](#disable-matdef) and macro [`\matdef`](#matdef).
### `\enablematdef`

Enable the `\matdef` macro. See also option [`enable-matdef`](#enable-matdef) and macro [`\matdef`](#matdef).
### `\matdef`

Enabled by option `enable-matdef` and disabled by option `disable-matdef` (see also options [`enable-matdef`](#enable-matdef) and [`disable-matdef`](#disable-matdef)).

Use `\enablematdef` or `disable-matdef` to enable or disable `\matdef` manually (see also macros [`\enablematdef`](#enablematdef) or [`\disable-matdef`](#disablematdef)).

`\matdef` defines macros with no parameter by format `<control> -> <replacement>;`.

```TeX
\matdef{
    \foo -> mate;   % \def\foo{mate}
    \bar -> xart;   % \def\bar{xart}
}
\foo\bar            % output "matexart"
```

The space between `<control>` and `->` is optional, but the space between `->` and `<replacement>` is necessary.

## Author

### OrthoPole

- [https://github.com/topfyf](https://github.com/topfyf)
- topfyf@qq.com

## License

Copyright &copy; 2023, [OrthoPole](#orthopole). Release under [GNU General Public License 3.0](https://www.gnu.org/licenses/gpl-3.0.html).
