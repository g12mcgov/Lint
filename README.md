# Lint

Lint is a simple command line tool used for multi-language linting. 

![demo](http://i1158.photobucket.com/albums/p618/g12mcgov/demo_2.gif)

**Example:**

```lint --type=csv ~/Downloads/example.csv```

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

Download and install the `lint` script via:

    $ curl -L https://github.com/g12mcgov/Lint/raw/master/lint > lint && mv lint /usr/local/bin/lint && chmod +x /usr/local/bin/lint

(only works for Unix based systems)
