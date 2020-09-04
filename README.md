# My Pandoc Highlight Theme

Default Pandoc highlight themes are kind of boring. Here is the highlight theme I like to use. You can make your own by editing the `.theme` file.

For RMarkdown,  your header should include something like:

```YAML
---
output:
  pdf_document:
    pandoc_args: "--highlight-style=adam.theme"
---
```

The `.theme` file should also be in the same folder as the Rmd file you are knitting otherwise the path to the `.theme` file should be specified.

Example `.Rmd` file [here](https://github.com/adamshen1/adam-highlight-theme/blob/master/example.Rmd).

Example pdf output [here](https://github.com/adamshen1/adam-highlight-theme/blob/master/example.pdf).
