# Discourse Highlight.js Zig

This Discourse theme component adds syntax highlighting for the `zig` programming language.

## Installation

1. Add a "remote" theme component in Discourse admin console,
use `https://github.com/jecolon/discourse-highlightjs-zig` repository URL.

2. Add `zig` to the `highlighted languages` list in Discourse Settings.


## How it works

Discourse uses Highlight.js library to highlight code syntax.

Note that Discourse does not use the latest version of Highlight.js. To check the hljs version being used by your 
Discourse instance, open your Discourse website, go to the developer console, and type: `hljs.versionString`.

This means the online documentation of Highlight.js might not work for you, so you will need to choose the right 
release tag in GitHub and navigate to the `/docs`.

## Develop and test locally

While developing locally, edit `function zig_language_definition()` in file `_dev/shared.js`.

Open `_dev/test-syntax-highlight.html` in your browser to preview highlighted `zig` code. It is also where you add more 
sample `zig` code for the preview.

This file is ignored by Discourse and is only used to preview syntax highlighting locally before pushing the new version.

Once done, copy the `zig_language_definition()` language definition function over to `common/head_tag.html`, which is 
the file loaded by Discourse.

**Note**. When updating the version of Highlight.js, you also need to update the version referenced by the `<script>` tag:

`<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.6.0/highlight.min.js"></script>`

## CSS Styles

Syntax highlighting styles are defined in `common/common.scss`. Note that even though it will be SASS-compiled by 
Discourse when the theme is installed, we don't use any of the SASS features in it because we want it to work in our 
local preview file. In fact, we load it as a `css` file in there, so it's not compiled.

Please keep this in mind when adding more styles.  We want our local develop preview file to keep functioning.

## Authors

After contributing, please don't forget to add yourself to the list:

* [Jose Colon](https://github.com/jecolon)
* Based on the excellent work by Anton Andriievskyi at https://github.com/Jai-Community/discourse-highlightjs-jai
