# `doctest_tui`

An ncurses TUI for running Python "doctests".

Note that this may work perfectly fine for some use cases, but it is still in an
"alpha" state and has some bugs, mainly that it does not successfully import
some files, for reasons I have not yet debugged.

## Usage

Ensure that you have `python3` installed and on your path, then clone this
repository, and place `doctest_tui` somewhere on your path somewhere on your
path.

Then, to run it, use the following command:

```bash
doctest_tui module_with_doctests.py more_doctests.py
```

Note that you can specify as many files as you would like as arguments, with
relative or absolute paths. If a path is not valid, `doctest_tui` will still
run, but the path will be highlighted in red in the top left corner. If no valid
paths are found in the arguments, then it will refuse to run and display help
information instead.

## Keymap

| Key                               | Action                |
|-----------------------------------|-----------------------|
| <kbd>q</kbd>                      | quit                  |
| <kbd>Tab</kbd>                    | focus next ui element |
| <kbd>Shift</kbd> + <kbd>Tab</kbd> | focus next ui element |
| <kbd>h</kbd> or <kbd>←</kbd>      | navigate left         |
| <kbd>j</kbd> or <kbd>↓</kbd>      | navigate down         |
| <kbd>k</kbd> or <kbd>↑</kbd>      | navigate up           |
| <kbd>l</kbd> or <kbd>→</kbd>      | navigate right        |
| <kbd>r</kbd>                      | update tests          |

## Contributing

Feel free to contribute in any way you'd like, there are two things I would
suggest though:

- Try to stick to vi-like keybindings, as far as it is possible in order to
  match the current keymap.
- If the functionality you're adding is not something you think most people will
  use, consider hiding it behind a keyboard shortcut, or adding configuration
  options

### Planned Improvements

- [ ] Debug failing imports.
- [ ] Add `python_ta` shortcut that pulls the configuration, max line length,
  allowed imports, etc. from the target file.
- [ ] Add horizontal and vertical scrolling for long doctests.
- [ ] Interactive debugging in the output window.
- [ ] pytest support?
- [ ] Improve data structure of `Functions.results` and `Functions.names`, and
  cut down on duplicate data.
