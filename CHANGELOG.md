## [0.3.2](https://github.com/hellux/jotdown/releases/tag/0.3.2) - 2023-09-06

### Changed

- Alphabetic list markers can only be one character long.

## [0.3.1](https://github.com/hellux/jotdown/releases/tag/0.3.1) - 2023-08-05

### Changed

- Block parser performance improved, up to 15% faster.
- Last `unsafe` block removed (#5).

### Fixed

- Do not require indent for continuing footnotes.
- Transfer classes from reference definitions to links.
- Allow line breaks in reference links (still match reference label).
- Remove excess newline after raw blocks.
- HTML renderer: fix missing `<p>` tags after ordered lists (#44).

## [0.3.0](https://github.com/hellux/jotdown/releases/tag/0.3.0) - 2023-05-16

### Added

- Source maps, via `Parser::into_offset_iter` (#39).

### Changed

- (breaking) `Render::render_event` has been removed (#36),
  `Render::{push,write}{,_borrowed}` take non-mutable reference of self.
- (breaking) Link definitions events are emmited (#36).
- (breaking) Footnote events are emitted as they are encountered (#36), instead
  of at the end of the document.
- Empty spans are parsed as spans when followed by URL, label or attributes.
- (breaking) Div class is non-optional, no class yields empty class string.
- (breaking) `Container::CodeBlock.lang` renamed to `language`.
- (breaking) Code block language is non-optional, no specfier yields empty
  string.
- Only ASCII whitespace is considered whitespace (#40).
- Performance improved, up to 20% faster (#40).

### Fixed

- Unclosed attributes after verbatim.
- Referenced headings with whitespace.
- Order of heading ids during lookup.
- Closing of math containers that end with backticks.
- Sole math containers in table cells.
- Attributes inside verbatim (#41).

## [0.2.1](https://github.com/hellux/jotdown/releases/tag/0.2.1) - 2023-04-25

### Changed

- Performance improved for inline parsing, up to 80% faster (#37).

### Fixed

- URL of autolink exit event (#35).

## [0.2.0](https://github.com/hellux/jotdown/releases/tag/0.2.0) - 2023-04-04

### Added

- Arguments to CLI (#8).
- Render trait (#12).
- Support for escapes in attributes (#19).
- Clone implementation for `Event` (#24).
- Rendering of borrowed `Event`s (#29).
- Clone implementation for `Parser` (#30).

### Changed

- (breaking) HTML rendering is done via the Render trait (#12).
- (breaking) Attribute values are represented by a custom `AttributeValue` type
  (#19).
- (breaking) Link `Event`s now expose unresolved reference labels (#27).
- Performance improved for inline parsing, up to 40% faster (#30).

### Fixed

- Incorrect parsing when multiple list items start on same line.
- List tightness.
- Disappearing attributes after inline verbatim (#16).
- Invalid HTML due to img tags (#25).
- Email autolink events not marked as Email (#27).
- Link text reference labels not stripping formatting (#22).
- Disappearing consecutive attribute sets (#34).

## [0.1.0](https://github.com/hellux/jotdown/releases/tag/0.1.0) - 2023-02-05

Initial Release.
