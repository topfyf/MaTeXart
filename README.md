# MaTeXart
> A package with useful macros and environments for math papers.

## Description
This is a package created for math article authors. The functions mainly include two parts: lots of math commands, and macros helping defining math commands and environments. The main purpose is to automate the process of defining commands and environment, resulting in saving a lot of time for users.

## Install
1. Download the whole folder and copy it into the package folder of your $\LaTeX$.
2. Execute `texhash` to update the package list (sometimes require `sudo`).

## Options

| Option | Default | Description |
| --- | --- | --- |
| `disable-loopstring` | No | Disable the `\loopstring` and `\loopstringwhile` macros |
| `disable-matdef` | No | Disable the `\matdef` macro |
| `enable-loopstring` | Yes | Enable the `\loopstring` and `\loopstringwhile` macros |
| `enable-matdef` | Yes | Enable the `\matdef` macro |

### `disable-loopstring`
Disable the `\loopstring` and `\loopstringwhile` macros. See also option [`enable-loopstring`](#enable-loopstring) and macros [`\loopstring`](#loopstring), [`\loopstringwhile`](#loopstringwhile).
### `disable-matdef`
Disable the `\matdef` macro. See also option [`enable-matdef`](#enable-matdef) and macro [`\matdef`](#matdef).

### `enable-loopstring`
Enable the `\loopstring` and `\loopstringwhile` macros. See also option [`disable-loopstring`](#disable-loopstring) and macros [`\loopstring`](#loopstring), [`\loopstringwhile`](#loopstringwhile).
### `enable-matdef`
Enable the `\matdef` macro. See also option [`disable-matdef`](#disable-matdef) and macro [`\matdef`](#matdef).

## Macros
| Macro | Description |
| --- | --- |
| `\disableloopstring` | Disable the `\loopstring` and `\loopstringwhile` macros |
| `\disablematdef` | Disable the `\matdef` macro |
| `\enableloopstring` | Enable the `\loopstring` and `\loopstringwhile` macros |
| `\enablematdef` | Enable the `\matdef` macro |
| `\loopstring` | Execute the input macro over each input character |
| `\loopstringwhile` | Execute the input macro over each input character while the input condition is true |
| `\matdef` | Define macros with no parameter by `<control> -> <replacement>;` |

### `\disableloopstring`
Disable the `\loopstring` and `\loopstringwhile` macros. See also option [`enable-loopstring`](#enable-loopstring) and macros [`\loopstring`](#loopstring), [`\loopstringwhile`](#loopstringwhile).
### `\disablematdef`
Disable the `\matdef` macro. See also option [`disable-matdef`](#disable-matdef) and macro [`\matdef`](#matdef).

### `\enableloopstring`
Enable the `\loopstring` and `\loopstringwhile` macros. See also option [`disable-loopstring`](#disable-loopstring) and macros [`\loopstring`](#loopstring), [`\loopstringwhile`](#loopstringwhile).
### `\enablematdef`
Enable the `\matdef` macro. See also option [`enable-matdef`](#enable-matdef) and macro [`\matdef`](#matdef).

### `\loopstring`
Enabled by option `enable-loopstring` and disabled by option `disable-loopstring` (see also options [`enable-loopstring`](#enable-loopstring) and [`disable-loopstring`](#disable-loopstring)).

Use `\enableloopstring` or `\disableloopstring` to enable or disable `\loopstring` manually (see also macros [`\enableloopstring`](#enable-loopstring) and [`\disableloopstring`](#disable-loopstring)).

`\loopstring` help you scan through each character in the input string and execute a macro over them. It mainly functions like inserting the input macro before each input character.

```TeX
% ** \long\def\loopstring#1#2 **
% Description: execute #2 on each character in #1
% Example:
\loopstring{Hello World!}\uppercase     % output "HELLO WORLD!"
```
**Caution**. The parameter `#2` may not be a balanced text.

### `\loopstringwhile`
Enabled by option `enable-loopstring` and disabled by option `disable-loopstring` (see also options [`enable-loopstring`](#enable-loopstring) and [`disable-loopstring`](#disable-loopstring)).

Use `\enableloopstring` or `\disableloopstring` to enable or disable `\loopstring` manually (see also macros [`\enableloopstring`](#enable-loopstring) and [`\disableloopstring`](#disable-loopstring)).

`\loopstringwhile` help you scan through each character in the input string and execute a macro over them while the input condition is true.

```TeX
% ** \long\def\loopstringwhile#1#2#3 **
% Description: execute #3 on each character in #2 while #1 is true
% Example:
\newif\ifcontinue\continuetrue
\def\test#1{#1\ifx o#1\continuefalse\fi}
\loopstring\ifcontinue{Hello World!}\test     % output "Hello"
```
**Caution**. The parameter `#1,#3` may not be balanced texts.

### `\matdef`
Enabled by option `enable-matdef` and disabled by option `disable-matdef` (see also options [`enable-matdef`](#enable-matdef) and [`disable-matdef`](#disable-matdef)).

Use `\enablematdef` or `\disablematdef` to enable or disable `\matdef` manually (see also macros [`\enablematdef`](#enablematdef) and [`\disablematdef`](#disablematdef)).

`\matdef` defines macros with no parameter by format `<control> -> <replacement>;`.

```TeX
% ** \long\def\matdef#1 **
% Description: define macros with no parameter by <control sequence> -> <replacement text>
% Example:
\matdef{
    \foo -> mate;   % \def\foo{mate}
    \bar -> xart;   % \def\bar{xart}
}
\foo\bar            % output "matexart"
```

The space between `<control>` and `->` is optional, but the space between `->` and `<replacement>` is necessary.

## Math Commands
| Command | Description | Effect |
| - | - | - |
| `\A,\B,\C,...` | `\mathbb` | $\mathbb{A},\mathbb{B},\mathbb{C},\cdots$ |
| `\AA,\BB,\CC,...` | `\mathcal` | $\mathcal{A},\mathcal{B},\mathcal{C},\cdots$ |
| `\AAA,\BBB,\CCC,...` | `\mathfrak` | $\mathfrak{A},\mathfrak{B},\mathfrak{C},\cdots$ |
| `\aa,\bb,\cc,...` | `\mathscr` | $\mathscr{A},\mathscr{B},\mathscr{C},\cdots$ |
| `\aaa,\bbb,\ccc,...` | `\mathfrak` | $\mathfrak{a},\mathfrak{b},\mathfrak{c},\cdots$ |
| `\GL` | general linear group | $\operatorname{\mathbb{GL}}$ |
| `\SL` | special linear group | $\operatorname{\mathbb{SL}}$ |
| `\SO` | special orthogonal group | $\operatorname{\mathbb{SO}}$ |
| `\SU` | special unitary group | $\operatorname{\mathbb{SU}}$ |
| `\PGL` | projective general linear group | $\operatorname{\mathbb{\bold PGL}}$ |
| `\PSL` | projective special linear group | $\operatorname{\mathbb{\bold PSL}}$ |
| `\ab` | maximum abelian extension | $\operatorname{\mathnormal{ab}}$ |
| `\adj` | adjoint of a matrix | $\operatorname{adj}$ |
| `\al` | algebraic closure | $\operatorname{\mathnormal{al}}$ |
| `\Alt` | alternative space | $\operatorname{\mathnormal{\mathcal Alt}}$ |
| `\Aut` | automorphism group | $\operatorname{\mathnormal{\mathcal Aut}}$ |
| `\Ann` | annihilator | $\operatorname{\mathnormal{\mathcal Ann}}$ |
| `\Br` | Brauer group | $\operatorname{\mathnormal{\mathcal Br}}$ |
| `\coim` | coimage | $\operatorname{coim}$ |
| `\coker` | cokernel | $\operatorname{coker}$ |
| `\Cl` | ideal class group | $\operatorname{\mathnormal{\mathcal Cl}}$ |
| `\Cor` | corestriction map | $\operatorname{\mathnormal{\mathcal Cl}}$ |
| `\Char` | characteristic | $\operatorname{\mathnormal{\mathcal Char}}$ |
| `\diag` | diagonal matrix | $\operatorname{diag}$ |
| `\disc` | discriminant | $\operatorname{disc}$ |
| `\Div` | divisor group | $\operatorname{\mathnormal{\mathcal Div}}$ |
| `\End` | endormorphism set | $\operatorname{\mathnormal{\mathcal End}}$ |
| `\Ext` | Ext functor | $\operatorname{\mathnormal{\mathcal Ext}}$ |
| `\Frac` | field of fractions | $\operatorname{\mathnormal{\mathcal Frac}}$ |
| `\Gal` | Galois group | $\operatorname{\mathnormal{\mathcal Gal}}$ |
| `\hatoplus` | a direct sum with a hat | $\hat\oplus$ |
| `\Hom` | homomorphism set | $\operatorname{\mathnormal{\mathcal Hom}}$ |
| `\id` | identity map | $\operatorname{id}$ |
| `\im` | image | $\operatorname{im}$ |
| `\inv` | Hasse invariant | $\operatorname{inv}$ |
| `\Inf` | inflation map | $\operatorname{\mathnormal{\mathcal Inf}}$ |
| `\Irr` | minimum polynomial | $\operatorname{\mathnormal{\mathcal Irr}}$ |
| `\Mor` | morphism set | $\operatorname{\mathnormal{\mathcal Mor}}$ |
| `\nr` | maximum non-ramified extension | $\operatorname{\mathnormal{nr}}$ |
| `\Nm` | norm map | $\operatorname{\mathnormal{\mathcal Nm}}$ |
| `\ord` | order | $\operatorname{ord}$ |
| `\Orb` | orbit | $\operatorname{\mathnormal{\mathcal Orb}}$ |
| `\rad` | radical | $\operatorname{rad}$ |
| `\rank` | rank | $\operatorname{rank}$ |
| `\Res` | residue | $\operatorname{\mathnormal{\mathcal Res}}$ |
| `\sep` | separable closure | $\operatorname{\mathnormal{sep}}$ |
| `\sign` | sign of a number or a permutation | $\operatorname{sign}$ |
| `\Stab` | stablizer | $\operatorname{\mathnormal{\mathcal Stab}}$ |
| `\tr` | trace | $\operatorname{tr}$ |
| `\Tr` | trace map | $\operatorname{\mathnormal{\mathcal Tr}}$ |
| `\Tor` | Tor functor | $\operatorname{\mathnormal{\mathcal Tor}}$ |
| `\ur` | maximum unramified extension | $\operatorname{\mathnormal{ur}}$ |
| `\vol` | volumne | $\operatorname{vol}$ |
| `\psum` | a sum with a prime | invalid in Markdown |
| `\pprod` | a product with a prime | invalid in Markdown |

## Author

### OrthoPole
- [https://github.com/topfyf](https://github.com/topfyf)
- topfyf@qq.com

## License

Copyright &copy; 2023, [OrthoPole](#orthopole). Release under [GNU General Public License 3.0](https://www.gnu.org/licenses/gpl-3.0.html).
