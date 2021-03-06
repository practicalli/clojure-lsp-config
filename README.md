## Practicalli Clojure LSP Configuration

Custom snippets in Clojure LSP format (EDN).  Practicalli designed snippets to encourage communication of the code purpose.

## Install

Clone the repository to the user level configuration location for Clojure LSP, either `$XDG_CONFIG_HOME/clojure-lsp` or if `XDG_CONFIG_HOME` is not set, `$HOME/.config/clojure-lsp`


## Clojure LSP configuration

Include `:extra-paths` and `:extra-deps` from project & user level aliases in LSP classpath.  e.g. support a custom `user` namespace in `dev/user.clj`

```clojure
 :source-aliases #{:dev :test :env/dev :env/test :lib/reloaded}
```

Include Java Sources installed via Debian / Ubuntu package `openjdk-17-source` to support calls to Java Objects and Methods.

```clojure
 :java
 {:jdk-source-uri       "file:///usr/lib/jvm/openjdk-17/lib/src.zip" ;;
  :home-path            nil ;; jdk-source-uri takes precedence
  :download-jdk-source? false}
```

Clean namespace `ns` forms but do not sort require names

```clojure
 :clean {:automatically-after-ns-refactor true
         :ns-inner-blocks-indentation     :next-line
         :ns-import-classes-indentation   :next-line
         :sort {:ns      false
                :require false
                :import  false
                :import-classes {:classes-per-line 3} ;; -1 for all in single line
                :refer {:max-line-length 80}}}
```


Use `^private` metadata for private function definitions rather than `defn-`

```clojure
 :use-metadata-for-privacy? true
```

Location of [cljfmt configuration](cljfmt.edn) for formatting, path relative to project root.  The defaults for cljfmt are used, except `:remove-consecutive-blank-lines?` which is set to false to enable more readable code.

```clojure
 :cljfmt-config-path "cljfmt.edn"
```

> [cljfmt configuration](cljfmt.edn) included example `:indents` rules for clojure.core, compojure, fuzzy rules and examples used by the Clojure LSP maintainer.


## Custom snippets

[Snippets created by Practicalli](https://practical.li/spacemacs/snippets/clojure-lsp/practicalli-snippets.html) are documents in [Practicalli Spacemacs](https://practical.li/spacemacs/snippets/clojure-lsp/practicalli-snippets.html)

### Docs / comments
* `comment-heading` - describe purpose of the namespace
* `comment-separator` - logically separate code sections, helps identify opportunities to refactor to other name spaces
* `comment-section` - logically separate large code sections with start and end line comments
* `wrap-reader-comment` - insert reader comment macro, `#_` before current form, informing Clojure reader to ignore next form

### Repl Driven Development
* `rich-comment` - comment block
* `rich-comment-rdd` - comment block with ignore :redefined-var for repl experiments
* `rich-comment-hotload` - comment block with add-libs code for hotloading libraries in Clojure CLI repl
* `wrap-rich-comment` - wrap current form with comment reader macro
* `require-rdd` - add a require expression, for adding a require in a rich comment block for RDD

### Standard library functions
* `def` - def with docstring
* `def-` - private def with docstring
* `defn` - defn with docstring
* `defn-` private defn with docstring
* `ns` - namespace form with docstring

### Clojure CLI deps.edn aliases
* `deps-alias` - add Clojure CLI alias
* `deps-maven` - add a maven style dependency
* `deps-git` - add a git style dependency using `:git/sha`
* `deps-git-tag` - as above including `:git/tag`
* `deps-git-url` - add git style dependency using git url (url taken from dependency name as it is typed - mirrored placeholder)
* `deps-local` - add a `:local/root` dependency

### Requiring dependencies
* `require-rdd` - add a require expression, for adding a require in a rich comment block for RDD
* `require` - simple require
* `require-refer` - require with `:refer`
* `require-as` - require with `:as` alias
* `use` - creates a require rather than the more troublesome use

### Unit testing
* `deftest` - creates a deftest with testing directive and one assertion
* `testing` - creates a testing testing directive and one assertion
* `is` - an assertion with placeholders for test function and expected results
