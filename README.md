# Console Traits

This crate is all about handling text consoles. Think XTerm, or a Powershell
prompt on Windows. They have a regular grid of monospaced characters, where
each character has a row number and a column number. There is a cursor, which
indicates where any new text will be displayed. When the text is displayed,
the cursor moves along. When text gets to the end of a row, the cursor pops
down to the start of the next line, and so on.

We're so familiar with these terminals, we forget there's actually a fair
amount of logic behind them. Especially when you consider [ANSI Escape
Codes](https://en.wikipedia.org/wiki/ANSI_escape_code).

This crate contains three basic traits, to help you add a console to your
`#![no_std]` Embedded Rust application.

* UnicodeConsole - for when your input/output devices have full Unicode
  support and can produce/receive either `char`s or `UTF-8` encoded bytes.
* AsciiConsole - for when your input/output devices only speak in bytes, which
  have some unspecified (but ASCII compatible) encoding, like Code Page 437,
  or ISO8859-1.
* BaseConsole - the common functionality for both of the above

## Changelog

### Unreleased Changes ([Source](https://github.com/rust-embedded-community/console-traits/tree/master) | [Changes](https://github.com/rust-embedded-community/compare/console-traits/v0.4.0...master))

* We're working on full ANSI escape sequence support in the `ansi_support`
  branch.

### v0.4.0 ([Source](https://github.com/rust-embedded-community/console-traits/tree/v0.4.0) | [Changes](https://github.com/rust-embedded-community/console-traits/compare/v0.4.0...v0.3.0))

* Contains the proprietary single character escape sequences from
  [Monotron](https://github.com/thejpster/monotron).
