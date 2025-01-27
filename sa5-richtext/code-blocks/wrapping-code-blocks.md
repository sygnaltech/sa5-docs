# Wrapping Code Blocks

As of 27-Aug-2024, Webflow's code blocks do not wrap. &#x20;

When you're dropping in something like a regex, which cannot have line breaks in it, it creates some UX inconveniences.&#x20;

## Goals

* We want to be able to wrap code blocks like this;&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Live example on <a href="https://sygnal.webflow.io/lessons/validating-emails">https://sygnal.webflow.io/lessons/validating-emails</a></p></figcaption></figure>

* Control by syntax type, e.g. Plain Text, JavaScript... which is set for each block&#x20;

Ideally;

* Ideally, block-specific control even within rich text elements&#x20;

Ideas;&#x20;

* Usurp line numbers as a wrapping control?&#x20;



## Usage Notes

### wfu-codeblock-wrap = ( no value )

Place this on any **Code Block**, or on a **Rich Text Block** to affect the Code Block elements it contains. &#x20;

After tagging your element, add an Embed in your page with the following code.

```html
<style>
[wfu-codeblock-wrap] code {
  white-space: pre-wrap !important;
}
</style>
```

To limit to code blocks with a specific language selected, you can add a class to the code selector, see Language Types below for the class name to use.&#x20;

```html
<style>
[wfu-codeblock-wrap] code.language-javascript {
  white-space: pre-wrap !important;
}
</style>
```

Future;

{% hint style="warning" %}
In the future we'll support wrapping on language-specific blocks in the SA5 lib directly.
{% endhint %}

* Specifying a language code will wrap only those languages identified
  * Several can be specified, comma-separated





## Language Types

_Work-in-progress._&#x20;

As of 27-Aug-2024 the list below contains the languages supported.  In most, the CSS class name applied to the Code Block is the lowercased language name prefixed with `language-(name)`.&#x20;

You can see this on the `<code>` element;

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>A Code Block set to JavaScript, showing <code>lauguage-javascript</code></p></figcaption></figure>

Some languages however vary that, for example C++ is classed as `language-cpp`.&#x20;

{% hint style="warning" %}
**IMPORTANT**\
The list below is a quick attempt to guess what CSS class Webflow will generate as the language codes for each, it has not been verified for many.  Use Chrome inspector to double-check.&#x20;
{% endhint %}

Use the Code.  If you're uncertain, check the course code in Chrome inspector

| Original     | Lowercase    | CSS Class             | Code         |
| ------------ | ------------ | --------------------- | ------------ |
| Arduino      | arduino      | language-arduino      | arduino      |
| Bash         | bash         | language-bash         | bash         |
| Basic        | basic        | language-basic        | basic        |
| BNF          | bnf          | language-bnf          | bnf          |
| C            | c            | language-c            | c            |
| Clojure      | clojure      | language-clojure      | clojure      |
| CoffeeScript | coffeescript | language-coffeescript | coffeescript |
| Coq          | coq          | language-coq          | coq          |
| C++          | c++          | language-cpp          | cpp          |
| CSS          | css          | language-css          | css          |
| Dart         | dart         | language-dart         | dart         |
| Diff         | diff         | language-diff         | diff         |
| Docker       | docker       | language-docker       | docker       |
| EBNF         | ebnf         | language-ebnf         | ebnf         |
| Elixir       | elixir       | language-elixir       | elixir       |
| Elm          | elm          | language-elm          | elm          |
| Erlang       | erlang       | language-erlang       | erlang       |
| Gherkin      | gherkin      | language-gherkin      | gherkin      |
| GLSL         | glsl         | language-glsl         | glsl         |
| Go           | go           | language-go           | go           |
| Groovy       | groovy       | language-groovy       | groovy       |
| Haskell      | haskell      | language-haskell      | haskell      |
| HTML         | html         | language-html         | html         |
| Java         | java         | language-java         | java         |
| JavaScript   | javascript   | language-javascript   | javascript   |
| JSON         | json         | language-json         | json         |
| Julia        | julia        | language-julia        | julia        |
| Kotlin       | kotlin       | language-kotlin       | kotlin       |
| LaTeX        | latex        | language-latex        | latex        |
| Less         | less         | language-less         | less         |
| Lisp         | lisp         | language-lisp         | lisp         |
| LiveScript   | livescript   | language-livescript   | livescript   |
| LLVM IR      | llvm ir      | language-llvm-ir      | llvm-ir      |
| Lua          | lua          | language-lua          | lua          |
| Makefile     | makefile     | language-makefile     | makefile     |
| Markdown     | markdown     | language-markdown     | markdown     |
| Mathematica  | mathematica  | language-mathematica  | mathematica  |
| MATLAB       | matlab       | language-matlab       | matlab       |
| Nix          | nix          | language-nix          | nix          |
| Objective-C  | objective-c  | language-objectivec   | objectivec   |
| OCaml        | ocaml        | language-ocaml        | ocaml        |
| Perl         | perl         | language-perl         | perl         |
| PHP          | php          | language-php          | php          |
| Plain Text   | plain text   | language-plaintext    | plaintext    |
| PowerShell   | powershell   | language-powershell   | powershell   |
| Prolog       | prolog       | language-prolog       | prolog       |
| Protobuf     | protobuf     | language-protobuf     | protobuf     |
| Python       | python       | language-python       | python       |
| R            | r            | language-r            | r            |
| Reason       | reason       | language-reason       | reason       |
| Ruby         | ruby         | language-ruby         | ruby         |
| Rust         | rust         | language-rust         | rust         |
| Sass         | sass         | language-sass         | sass         |
| Scala        | scala        | language-scala        | scala        |
| Scheme       | scheme       | language-scheme       | scheme       |
| SCSS         | scss         | language-scss         | scss         |
| Shell        | shell        | language-shell        | shell        |
| SQL          | sql          | language-sql          | sql          |
| Swift        | swift        | language-swift        | swift        |
| TypeScript   | typescript   | language-typescript   | typescript   |
| VB.NET       | vb.net       | language-vbnet        | vbnet        |
| Verilog      | verilog      | language-verilog      | verilog      |
| VHDL         | vhdl         | language-vhdl         | vhdl         |
| XML          | xml          | language-xml          | xml          |
| YAML         | yaml         | language-yaml         | yaml         |











## Technical Notes

Must force the `<code>` element to pre-wrap.

