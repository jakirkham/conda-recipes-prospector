#Purpose

This is a collection of scripts to build [`prospector`]( https://github.com/landscapeio/prospector ) with [`conda`]( https://github.com/conda/conda ). Prospector takes a variety of common python linting tools and gives them a common interface and combines their results together. It was developed and is maintained by [landscape.io]( http://landscape.io ) where it is used to perform continuous code analysis and linting. In order to ensure projects using [landscape.io]( http://landscape.io ) and perform this analysis and linting offline, it was necessary to build `prospector`. However, many of the tools required were not available through `conda` and we wanted a way to build everything without relying on `pip`. So, recipes were added here for everything that could not be directly installed.

#Usage

This is very straightforward to use. Simply run `conda build prospector`.

#Patch notes

It became apparent that `pylint` had problems building due to its inclusion of syntactically bad or Python 3 only source code as part of its test data. As the Python interpreter tried to compile this problematic code, it would cause the install to fail. Even if we were able to bypass, these errors with `pylint` other packages that relied on `pylint` would import `pylint` and the interpreter would include and parse this test data. So, a number of patches were written to work around this problem. Similar, patches were required for `astroid`. These patches were written using `six` where possible to preserve the intent as best as could be done. In some cases, this wasn't possible and so code was commented or deleted. As a consequence, these patches likely have the consequence of causing test failures. So, this is something to be aware of.
