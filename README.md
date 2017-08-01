minimalRPackage
===============

This is the most minimal R package, which is useless at all

`R/`
----
We don't need `R/` directory to create an R package.

`NAMESPACE`
-----------
We do need `NAMESPACE` file, but it can be blank.

`DESCRIPTION`
-------------
We do need `DESCRIPTION` file and some fields in it. [Writing R Extensions](https://cran.r-project.org/doc/manuals/r-release/R-exts.html#The-DESCRIPTION-file) says:

> The ‘Package’, ‘Version’, ‘License’, ‘Description’, ‘Title’, ‘Author’, and ‘Maintainer’ fields are mandatory

But, in actual, it seems having only `Package` and `Version` is permitted.

### `Package`

Writing R Extensions says:

> The mandatory ‘Package’ field gives the name of the package. This should contain only (ASCII) letters, numbers and dot, have at least two characters and start with a letter and not end in a dot.

So, this is possible:

```
Package: aa
```

But this fails:

```
Package: a
```

### `Version`

Writing R Extensions says:

> The mandatory ‘Version’ field gives the version of the package. This is a sequence of at least two (and usually three) non-negative integers separated by single ‘.’ or ‘-’ characters. The canonical form is as shown in the example, and a version such as ‘0.01’ or ‘0.01.0’ will be handled as if it were ‘0.1-0’. It is not a decimal number, so for example 0.9 < 0.75 since 9 < 75. 

So, these are possible:

```
Version: 0.0
```

```
Version: 0-0
```

But this is not:

```
Version: 0
```
