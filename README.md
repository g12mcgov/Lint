# Lint

Lint is a simple command line tool used for multi-language linting. 

![demo](https://www.dropbox.com/s/mi3kghg2evmdqa3/demo.gif?dl=0)

**Example:**

```lint --type=csv ~/Downloads/exampke.csv```

Overview
=======

One of the annoyances I found with linting tools is that there's so many, yet no consistent means of being able to lint via a single tool for multiple languages. This bash tool uses other 3rd party linting libraries (i.e. [yaml-lint](https://github.com/Pryz/yaml-lint), [pylint](http://www.pylint.org/), [jsonlint](https://github.com/zaach/jsonlint), etc...).

It's easy to add another linter, via adding a block to the following case statement in the `lint` script:

    case $TYPE in
        "csv")
        csvlint "$1"
            ;;
        "yaml")
        yaml-lint "$1"
            ;;
        "python")
            pylint "$1"
            ;;
        "json")
            jsonlint "$1"
            ;;
        "html")
            tidy "$1"
            ;;
        ...


Installing
=======

Download the `lint` script and 