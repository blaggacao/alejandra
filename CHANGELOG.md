# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

<!--
Types of changes
- Added for new features.
- Changed for changes in existing functionality.
- Deprecated for soon-to-be removed features.
- Removed for now removed features.
- Fixed for any bug fixes.
- Security in case of vulnerabilities.
-->

### Changed

- Let-in expressions are now indented in the top-level of a file.
- Patterns avoid a new line after `@`:

  ```nix
  -        args @
  -        {
  +        args @ {
  ```

  ```nix
  -  }
  -  @ inp:
  +  } @ inp:
  ```

## [0.2.0] - 2022-02-17

### Added

- A `--version` flag to the CLI.
- Pre-built binaries for x86_64-linux and aarch64-linux.
- Support for inline comments on lists, attr-sets, and let-in expressions.

### Changed

- Made the logic of the `or-default` (`a or b`) node
  to be equal to the binary operator (`a $operator b`).
  This increases consistency across the same family of elements.
- Reduce 1 indentation level in `let-in` expressions,
  when the target expression is a parenthesis, attr-set, list, or string.
- String interpolations in multi-line strings
  now have a nice-looking indentation.

### Removed

- Users freedom to insert newlines
  before the `?` in pattern bindings (`a ? b`).

  Inserting a newline after the `?` is still possible.

  This increases consistency on where to break a long pattern binding.

- Space on empty containers (`[]`, `{}`).

### Fixed

- A bug in the current position counter
  caused a small percentage of multiline comments in Nixpkgs
  to be unaligned by one character.

## [0.1.0] - 2022-02-14

### Added

- Initial version
- A Changelog

## [0.0.0] - 2022-01-09

### Added

- The project :)

---

[unreleased]: https://github.com/kamadorueda/alejandra/compare/0.2.0...HEAD
[0.2.0]: https://github.com/kamadorueda/alejandra/compare/0.1.0...0.2.0
[0.1.0]: https://github.com/kamadorueda/alejandra/compare/0.0.0...0.1.0
[0.0.0]: https://github.com/kamadorueda/alejandra/compare/6adfbe8516bf6d9e896534e01118e1bc41f65425...0.0.0