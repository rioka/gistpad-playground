LSS, I've tried Obsidian again

> Vault is [here](./sample.zip)


Still troubles with code blocks and horizontal scrolling: by default, text wraps.

Custom CSS did not work apparently: 3 options were suggested by ChatGPT

Simple

```css
.markdown-reading-view code[class*="language-"] {
    overflow-x: scroll;
    white-space: pre;
    padding: 15px 0;
}
```

This should work both in edit and reading mode

```css

/* Horizontal scroll for code blocks in Reading mode */
.markdown-reading-view pre[class*="language-"] {
    overflow-x: auto;
    white-space: pre;
}

/* Horizontal scroll for code blocks in Live Preview (Edit mode) */
.cm-s-obsidian .cm-inline-code,
.cm-s-obsidian .cm-codeblock {
    overflow-x: auto;
    white-space: pre;
    display: block;
}

/* Optional: Add padding for better UX */
.markdown-reading-view pre[class*="language-"],
.cm-s-obsidian .cm-codeblock {
    padding: 8px;
}
```

This revised version should be compatible with latest version

```css

/* Horizontal scroll for code blocks in Reading mode */
.markdown-preview-view pre[class*="language-"] {
    overflow-x: auto;
    white-space: pre;
}

/* Horizontal scroll for code blocks in Live Preview (Edit mode) */
.markdown-source-view.mod-cm6 .cm-content pre {
    overflow-x: auto !important;
    white-space: pre !important;
}

/* Optional: Add padding for better UX */
.markdown-preview-view pre[class*="language-"],
.markdown-source-view.mod-cm6 .cm-content pre {
    padding: 8px;
}
```

LSS, none worked.

Some links provided, it imay be worth taking a look anyway:

- [A Simple CSS Trick to Deal with Horizontal Scrollbars in Code Blocks](https://yihui.org/en/2023/08/css-scrollbar/)
- https://forum.obsidian.md/t/live-preview-better-treatment-of-code-blocks-code-wrap-horizontal-scroll-and-smart-indent/33718?page=3
- https://github.com/kepano/obsidian-minimal/issues/604

## Plugins

- "Collapsible Code Blocks plugin" seems to be the best you can get, at least it works in reading mode
- "Style Settings" seems to have an option like "Scroll long lines", but I cannot find it.
- try [Dendron Importer](https://github.com/luisabellan/dendron-obsidian-importer)
- Use [Code Styler](github.com/mayurankv/Obsidian-Code-Styler) ⭐
- PlantUML
- Advanced Tables

## TO DO (blocked by FW proxy)

- check [Javalent's plugins](https://valentine195.github.io/index) and https://plugins.javalent.com/admonitions (the latter is blocked by FW proxy)
- https://forum.obsidian.md/t/cannot-browse-or-install-community-plugins-themes-cannot-read-properties-of-null/107284
- https://ptkm.net/