# My Pandoc Highlight Theme

Default Pandoc highlight themes are kind of boring. Here is the highlight theme I like to use. You can make your own by editing the `.theme` file (mine is based off of the `tango` highlight theme. 

## PDF Output

For PDF output, your header should include:

```YAML
---
output:
  pdf_document:
    pandoc_args: "--highlight-style=adam.theme"
---
```

The `.theme` file can either be in the same folder as the `.Rmd` file you are knitting, otherwise the path to the `.theme` file should be specified. **Note that this value must be a string and there cannot be a space before or after the `=` sign.**

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

The `my_template.html` is a template html file RMarkdown uses when knitting `.Rmd` files to html. You should be able to see the location of this template file in the RMarkdown console output whenver you knit a basic `.Rmd` file to html. This template file can be found in the `rmarkdown` package installation files under:

```
/rmarkdown/rmd/h/default.html
```

I would recommend making a copy of it and placing it in a location that is easily accessible.

Once again, the `.theme` file can be in the same folder as the `.Rmd` file you are knitting, otherwise a path to the `.theme` file should be specified. **Note that the file name or path does not need to be a string (though you can still supply a string).** You can also still specify `theme:` and `css:` values as usual.

Example `.Rmd` file [here](https://github.com/adamoshen/adam-highlight-theme/blob/master/html/demofile.Rmd).

Example HTML output [here](https://www.shena.ca/demofile.html).

The `.css` file I have included is used to change the code font from Courier New to Consolas, and is therefore optional.

### Why specify a template file?

Everything just "works" when we trick RMarkdown into thinking we have a custom html template, when we are really using the default one. Without specifying a template file, if your header looks like:

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

you will see from the RMarkdown console output that the specified highlight theme is accepted, but a `--no-highlight` is thrown in near the end, which nullifies your specified highlight theme.