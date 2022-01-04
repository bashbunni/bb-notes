## GoDoc

- Doc comments should be English sentences and paragraphs.
- They use no special formatting beyond indentation for preformatted text.
- Doc comments should begin with the noun they describe.

## Naming

Obviously, naming should be descriptive.

### Package Names

It's recommended that package names are used to add specificity to functions.
You don't want to "stutter", meaning you don't want to write something like: `bytes.BytesBuffer` when it's clear to write `bytes.Buffer`

#### Syntax

- all lowercase, no under_scores or mixedCaps
- simple nouns
- abbreviate only when using well-known developer abbreviations (e.g. sys)

### Package Contents

- avoid repetition
- simplify function names
- function names should match with package name to make for a readable type name

The Go blog recommends the following:

> If you cannot come up with a package name that’s a meaningful prefix for the package’s contents, the package abstraction boundary may be wrong. Write code that uses your package as a client would, and restructure your packages if the result seems poor. This approach will yield packages that are easier for clients to understand and for the package developers to maintain. - go blog

## Source

[package names - go blog](https://go.dev/blog/package-names)
[organizing go code - go blog](https://go.dev/blog/organizing-go-code)
