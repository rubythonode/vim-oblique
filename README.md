vim-oblique ![travis-ci](https://travis-ci.org/junegunn/vim-oblique.svg?branch=master)
===========

Improved `/`-search for Vim.

- Different highlight for the match under the cursor
- Automatically clears search highlight when cursor is moved
- Does not append short patterns to search history
- Readline key bindings
- Fuzzy-search
- Improved star-search (visual-mode, highlighting without moving)

Installation
------------

Use your favorite plugin manager. vim-oblique requires
[vim-pseudocl](https://github.com/junegunn/vim-pseudocl).

With [vim-plug](https://github.com/junegunn/vim-plug):

```vim
Plug 'junegunn/vim-pseudocl'
Plug 'junegunn/vim-oblique'
```

Usage
-----

vim-oblique overrides the following keys by default:

| Default Key | <Plug> map           | Description                                      |
| ----------- | -------------------- | ------------------------------------------------ |
| `/`         | `<Plug>(Oblique-/)`  | Forward search                                   |
| `?`         | `<Plug>(Oblique-?)`  | Backward search                                  |
| `z/`        | `<Plug>(Oblique-F/)` | Forward fuzzy-search                             |
| `z?`        | `<Plug>(Oblique-F?)` | Backward fuzzy-search                            |
| `n`         | `<Plug>(Oblique-n)`  | Repeat the last search                           |
| `N`         | `<Plug>(Oblique-N)`  | Repeat the last search in the opposite direction |
| `*`         | `<Plug>(Oblique-*)`  | Forward star-search (in normal and visual mode)  |
| `#`         | `<Plug>(Oblique-#)`  | Backward star-search (in normal and visual mode) |
| `g*`        | `<Plug>(Oblique-g*)` | Forward star-search (no word boundary match)     |
| `g#`        | `<Plug>(Oblique-g#)` | Backward star-search (no word boundary match)    |

(Unlike the default star-search, the overridden version will not move the cursor)

Customization
-------------

### Maps

Use the <Plug> maps in the above table to customize the maps.

### Options

- `g:oblique#min_length` (default: 3)
    - Patterns shorter than this will not be added to search history
- `g:oblique#clear_highlight` (default: 1)
    - To clear search highlight or not
- `g:oblique#very_magic` (default: 0)
    - To start pattern with `\V` or not
- `g:oblique#enable_star_search` (default: 1)
- `g:oblique#enable_fuzzy_search` (default: 1)

### Highlighting

Define the following highlight groups to change the color:

- `ObliquePrompt` (default: linked to `Label`)
- `ObliqueLine` (default: linked to `None`)
- `ObliqueCurrentMatch` (default: linked to `IncSearch`)

#### Example

```vim
hi! def link ObliqueCurrentMatch Keyword
hi! def link ObliquePrompt       Structure
hi! def link ObliqueLine         String
```

License
-------

MIT

