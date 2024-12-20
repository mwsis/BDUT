# BDUT <!-- omit in toc -->

**B**rain-**D**ead **U**nit-**T**esting, for C and C++.

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Installation](#installation)
  - [CMake installation](#cmake-installation)
  - [Manual installation](#manual-installation)
- [Examples](#examples)
- [Project Information](#project-information)
  - [Where to get help](#where-to-get-help)
  - [Contribution guidelines](#contribution-guidelines)
  - [Dependencies](#dependencies)
  - [Related projects](#related-projects)
  - [License](#license)


## Introduction

**B**rain-**D**ead **U**nit-**T**esting, is a very simple - simplistic, in fact - small, header-only, standalone library for C and C++. Its intent is to be bundled into other projects for which it is not desired to couple to a more sophisticated library.


## Installation

### CMake installation

Currently, **CMake** support is not yet provided.


### Manual installation

Since **BDUT** is intended to be bundled into other open-source libraries, the simplest way to use it is to add a directory **bdut** under your project's **include** directory, into which you can then simply copy **bdut.h**.


## Examples

**BDUT** is included simply into any C or C++ project by `#include`ing its header file, as in:

```C
/* examples/c/example_1 */

#include <bdut/bdut.h>

int main()
{
  BDUT_ASSERT_EQ(1, 2);

  return 0;
}
```

The output of this will be along the lines of:

```bash
~/open-source/BDUT/examples/c/example_1/main.cpp:7:main: assertion failed: actual value of `2` not equal-to expected value `1`
```

or a in:

```C++
/* examples/cpp/example_1 */

#include <bdut/bdut.h>

#include <iostream>


int main(int argc, char* argv[])
{
    BDUT_ASSERT_STRING_CONTAINS("", "abcdefghijklmnopqrstuvwxyz");
    BDUT_ASSERT_STRING_CONTAINS("abc", "abcdefghijklmnopqrstuvwxyz");

    /* this one will fail */
    BDUT_ASSERT_STRING_CONTAINS("abd", "abcdefghijklmnopqrstuvwxyz");

    return 0;
}
```

The output of this will be along the lines of:

```bash
~/open-source/BDUT/examples/cpp/example_1/main.cpp:15:main: assertion failed: actual string 'abcdefghijklmnopqrstuvwxyz' does not contain search string 'abd'
```


## Project Information

### Where to get help

[GitHub Page](https://github.com/synesissoftware/BDUT "GitHub Page")


### Contribution guidelines

Defect reports, feature requests, and pull requests are welcome on https://github.com/synesissoftware/BDUT.


### Dependencies

**BDUT** has no dependencies.


### Related projects

Projects in which **BDUT** is used for testing include:

* [**b64**](https://github.com/synesissoftware/b64)
* [**cstring**](https://github.com/synesissoftware/cstring)
* [**shwild**](https://github.com/synesissoftware/shwild)


### License

**BDUT** is released under the 3-clause BSD license. See [LICENSE](./LICENSE) for details.


<!-- ########################### end of file ########################### -->

