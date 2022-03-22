# My Pandoc Highlight Theme

Default Pandoc highlight themes are kind of boring. Here is the highlight theme
I like to use. You can make your own by editing the `.theme` file (mine is based
off of the `tango` highlight theme).

---

For additional examples of Pandoc highlight themes, see
[`adamoshen/highlight-demo`](https://github.com/adamoshen/highlight-demo/).
If you wish to apply syntax highlighting using PrismJS (HTML only) instead of
a Pandoc highlight theme, see
[`adamoshen/prismr`](https://github.com/adamoshen/prismr/).

## PDF Output

```YAML
output:
  pdf_document:
    highlight: adam.theme
```
The `.theme` file can be in the same folder as the `.Rmd` file you are knitting,
otherwise the path to the `.theme` file should be specified.

## HTML Output

```YAML
output:
  html_document:
    highlight: adam.theme
```

---

For the change log and instructions on using the highlight theme with RStudio
1.3, see the wiki.
