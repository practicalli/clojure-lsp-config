## Practicalli Clojure LSP Configuration

Custom snippets in Clojure LSP format (EDN).  Practicalli designed snippets to encourage communication of the code purpose.

## Install

Clone the repository to the user level configuration location for Clojure LSP, either `$XDG_CONFIG_HOME/clojure-lsp` or if not set, `$HOME/.lsp`


## Custom snippets

[Snippets created by Practicalli](https://practical.li/spacemacs/snippets/clojure-lsp/practicalli-snippets.html) are documents in [Practicalli Spacemacs](https://practical.li/spacemacs/snippets/clojure-lsp/practicalli-snippets.html)

| Snippet                | Description                                               |
|------------------------|-----------------------------------------------------------|
| `comment-heading`      | Heading describing the namespace using line comments      |
| `comment-separator`    | Logical separator for a namespace using line comments     |
| `def`                  | `def` with doc-string                                     |
| `def-`                 | `def ^:private` with doc-string                           |
| `defm`                 | `defn` with doc-string                                    |
| `defn-`                | `defn ^:private` with doc-string                          |
| `ns`                   | `ns` with doc-string                                      |
| `require`              | `require` directive with `:as` alias (within ns form)     |
| `require-rdd`          | `require` expression with `:as` alias (self-contained)    |
| `rich-comment`         | Rich comment using `comment` function                     |
| `rich-comment-rdd`     | Rich comment with clj-kondo ignore refined-var            |
| `rich-comment-hotload` | Rich comment with add-libs for hotload library dependency |
| `deftest`              | clojure.test `deftest` function with assertion grouping   |
| `testing`              | clojure.test `testing` function for assertion grouping    |
