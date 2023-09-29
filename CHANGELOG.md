# Change Log
All notable changes to this project will be documented in this file. This change log follows the conventions of [keepachangelog.com](http://keepachangelog.com/).

## [Unreleased]

## 2023-09-29
### Changed
- config: update source-aliases to use :dev/env user alias
- config: refine paths ignore regex with build & console-log patterns
- config: disable Java analysis, use significantly less resources

## 2023-03-18
## Added
- changelog as a record of major changes

### Changed
- complete rewrite of configuration, comments added where default values were not changed
- Clojure Lint GitHub action (with reviewdog), replacing setup-lsp-kondo (outdated)

### Resolve
- #1 - Clojure docstrings not showing in Emacs with Clojure-LSP
