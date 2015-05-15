#Purpose

This is a collection of scripts to build [`prospector`]( https://github.com/landscapeio/prospector ) with [`conda`]( https://github.com/conda/conda ). Prospector takes a variety of common python linting tools and gives them a common interface and combines their results together. It was developed and is maintained by [landscape.io]( http://landscape.io ) where it is used to perform continuous code analysis and linting. In order to ensure projects using [landscape.io]( http://landscape.io ) and perform this analysis and linting offline, it was necessary to build `prospector`. However, many of the tools required were not available through `conda` and we wanted a way to build everything without relying on `pip`. So, recipes were added here for everything that could not be directly installed.

#Usage

This is very straightforward to use. Simply run `conda build prospector`.
