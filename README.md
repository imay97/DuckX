<p align="center"><img src="https://github.com/amiremohamadi/DuckX/blob/master/img/logo.png" width="380"></p>

[![Build Status](https://travis-ci.com/amiremohamadi/DuckX.svg?branch=master)](https://travis-ci.com/amiremohamadi/DuckX)

# DuckX

**DuckX** is a library for creation of Office docx files

> DuckX helps you to work with docx files quickly in C++.

## Status ##

- Documents (docx) [Word]
	- Read

## Quick Start

Here's an example of how to use duckx to read a docx file; It opens a docx file named **file.docx** and goes over paragraphs and runs and prints them:
```c++
#include <iostream>
#include <duckx.hpp>

int main() {

    duckx::Document doc("file.docx");   

    doc.open();

    for (auto p = doc.paragraphs(); p.hasNext() ; p.next()) {
	for (auto r = p.runs(); r.hasNext(); r.next()) {
            std::cout << r.text() << std::endl;
        }
    }
}
```

**Note** that you must use -lduckx flag to compile your cpp file
<br/>
For example:
```bash
g++ sample1.cpp -lduckx
```

* See other [Examples](https://github.com/amiremohamadi/DuckX/tree/master/samples)


## Install ##

In order to use and compile duckx you need to have zlib.

#### Download dependencies

```bash
sudo apt-get install g++  # for ubuntu
sudo apt-get install libzip-dev  # for ubuntu

sudo dnf install gcc-c++  # for fedora
sudo dnf install zlib-devel  # for fedora
```

#### Compiling

The preferred way is to create a build folder
```bash
git clone https://github.com/amiremohamadi/DuckX.git
cd DuckX
mkdir build
sudo make
```

## Requirements ##

- [libzip](https://github.com/nih-at/libzip)
- [pugixml](https://github.com/zeux/pugixml)


### Licensing

This library is available to anybody free of charge, under the terms of MIT License (see LICENSE.md).
