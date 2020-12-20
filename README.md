# My Pandoc Highlight Theme

Default Pandoc highlight themes are kind of boring. Here is the highlight theme I like to use. You can make your own by editing the `.theme` file.

## PDF Output

For PDF output, your header should include:

```YAML
---
output:
  pdf_document:
    pandoc_args: "--highlight-style=adam.theme"
---
```

The `.theme` file can either be in the same folder as the `.Rmd` file you are knitting, otherwise the path to the `.theme` file should be specified. **Note that there cannot be a space before or after the `=` sign.**

Example `.Rmd` file [here](https://github.com/adamoshen/adam-highlight-theme/blob/master/pdf/example.Rmd).

Example PDF output [here](https://github.com/adamoshen/adam-highlight-theme/blob/master/pdf/example.pdf).

## HTML Output

This is slightly trickier with HTML output. The header will look something like:

```YAML
---
output: 
  html_document:
    template: my_template.html
    highlight: adam.theme
---
```

Once again, the `.theme` file can be in the same folder, otherwise a path to the `.theme` file should be specified. **Note that the file name or path does not need to be a string (you can still supply a string).** You can also still specify `theme:` and `css:` values as usual.

The `my_template.html` is a template html file used when knitting `.Rmd` files to plain html output (you should be able to see the location of this file in the RMarkdown console output when knitting to html). This template file can be found in the `rmarkdown` package installation files under:

```
/rmarkdown/rmd/h/default.html
```

Example `.Rmd` file [here](https://github.com/adamoshen/adam-highlight-theme/blob/master/html/demofile.Rmd).

Example HTML output [here](https://www.shena.ca/demofile.html).

The `.css` file I have included is only to change the code font from Courier New to Consolas, and is therefore optional.

### Why?

Without specifying a template file, if your header looks like:

```YAML
---
output:
  html_document:
    highlight: adam.theme
---
```

you will get an error that the theme you have specified is not one of the supported highlight themes.

Alternatively, if you try something like:

```YAML
---
output: 
  html_document:
    pandoc_args: "--highlight-style=adam.theme"
---
```

you will see from the RMarkdown console output that the specified highlight theme is accepted, but Pandoc throws in a `--no-highlight` afterwards, essentially cancelling out your highlight theme.