---
layout: default
title: Documentation
nav_order: 5
description: "Installation and usage."
permalink: /documentation.html
---

# Documentation

```
ATTENTION: This page is not complete for the latest version. 
It will be completed as soon as possible.
```

## Overview

Aestimo 1D is a 1-Dimensional Self-consistent Schrödinger-Poisson Solver for semiconductor heterostructures. Aestimo 1D is started as a hobby at the beginning of 2012, and become a usable tool which can be used as a co-tool in an educational and scientific work.

Hope that it also works for you. Please do not hesitate to [contact](https://github.com/aestimosolver/aestimo/issues/new/choose) us in case of any issues found.

The documentation material on this page is copyrighted. Reuse of the material on this wiki is permitted under GNU Free Documentation License 1.3.

### Current features

* Material and alloys: GaAs, AlAs , InAs, InP, AlP, GaP, GaN, InN, AlN, CdO, MgO, ZnO, Si, Ge, AlGaAs, InGaAs, GaAsP, InAsP, InGaP, AlInP, AlGaN, InGaN, AlInN, MgZnO, CdZnO, InGaAsP and AlGaInN.
* Band structure for gamma electrons and heavy, light and split-off holes,
* Effective-mass method for electrons and 3×3 k.p method for holes,
* Carrier concentrations for gamma electrons and heavy, light and split-off holes,
* Electric field distribution,
* Electron wavefunctions,
* Non-parabolicity,
* External electric field,
* Strain for valance band calculations,

## Getting Started

Aestimo 1D can work on Linux systems. To work on Windows systems, you can use [WSL](https://docs.microsoft.com/en-us/windows/wsl/install). To work without any dependency problems, we suggest to you to use conda package system. With conda, user can create environments and install any software without living any dependency problem.

### Prerequisites

If you do not prefer to use conda, you will need to have a recent version of Python and required libraries installed on your computer. For this, please refer to Python Website, where binary packages for most platforms can be found. Additionally, you need libraries called numpy, matplotlib, scipy and pylab. You use pip command to install these packages (Example: pip install numpy).

For Macintosh, Python is preinstalled and related libraries can be found at Pythonmac Directory.

### Conda installation

Download and install the miniconda. You can say ‘yes’ or ‘no’ to initialization after installing it:

    $ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    $ chmod +x Miniconda3-latest-Linux-x86_64.sh
    $ ./Miniconda3-latest-Linux-x86_64.sh

then you can update miniconda:

    $ eval "$(/home/$USER/miniconda3/bin/conda shell.bash hook)"
    $ conda update conda

Now, we can create an environment (here 'aes' name is used. You can use any name) and activate it:

    $ conda create --name aes
    $ conda activate aes

Then, install numpy, scipy, pylab and matplotlib

    $ conda install -c conda-forge numpy scipy matplotlib pylab

### Download and Installation of Aestimo 1D

The latest version of the program is available in zipped form from [this link](https://github.com/aestimosolver/aestimo/archive/refs/heads/master.zip).

In your home folder (~), let's download the latest development release (you can prefer stable release also, please visit https://www.aestimosolver.org to get the latest URL)

    cd ~
    wget [https://github.com/lrgresearch/gpaw-tools/archive/refs/heads/main.zip](https://github.com/aestimosolver/aestimo/archive/refs/heads/master.zip)
    unzip master.zip

All files will be extracted to a folder called `aestimo-master`. We need to make some files executable, and add this folder to `~/.bashrc` file to system-wide reach.

    cd aestimo-master/
    chmod +x aestimo.py
    nano ~/.bashrc

Add the following line at the end of your ``~/.bashrc`` file.

    export PATH=/home/YOURUSERNAME/aestimo-master:$PATH


After editing ~/.bashrc file quit the current shell session and start a new one (or you can use `source ~/.bashrc` command). 



### Running the Code

First of all, user must prepare or use an input file. There are many example in the `examples` folder of the package:

    cd ~/aestimo-master/examples

There is also an important file called `config.py`. There are other options in this file. However, without changing anything most of the input files in examples folder will work. Let's try to run any of the input files in examples folder

    aestimo.py -i sample_1qw_barrierdope_ingaas.py

After running for under a minute, calculation will be finished. Results will be written to files under folder named with input file (Here, sample_1qw_barrierdope_ingaas). If user wants to see wavefunctions, electric field distribution, potential and sigma distribution after calculation `-d` argument can be used:

    aestimo.py -d -i sample_1qw_barrierdope_ingaas.py

To see the version of aestimo:

    aestimo.py -v

To see the help:

    aestimo.py -h
    
can be used.

## Aestimo Command Reference

### Format of Input File

aestimo input files are simple python files. Each line is a statement or a comment. Statements are shown as python variables. These variable are equalized to parameters. Right hand side of equal sign is the parameter part. Therefore, the statement/parameter pairs have the format as

```
statement = parameter
```

or

```
statement = [[param11, param12], [param21, param22]]
```

In addition to statement/parameter lines, lines can be also blank and comment lines. Comment lines are shown

```
# Comment line
```
Comments can also be added at the end of statement/parameter lines as

```
statement = parameter # Comment is at the end
```

In addition to these, there is python related lines. These lines are the first two lines of the file.

```
#!/usr/bin/env python 
# -*- coding: utf-8 -*-
```

First one is the line which shows the place of python executable in a UNIX-like system. Second line is about coding. These lines can stay as they. Because of input files are just python files, and the statements are python variables, statements in aestimo are sequence insensitive. Parameters may be one of four standard python types: float, integer, bool, string. All the parameter specification has the same format as

```
parameter_name = [number|integer|bool|string]
```

Statements and string parameters are mostly case sensitive.

### Statement Description Format
Will be here.

### General Settings
Will be here.

## Troubleshooting

* *Program is not converging!*: Convergence problem can be raised from mainly two reasons: Gridfactor is not small enough and structure is highly doped. Please use smaller gridfactor (<1nm) and low doping concentrations (<1e17 cm^-3).

## Copyright information

Aestimo 1D Schrodinger-Poisson Solver
Version v.0.6 - v.2.0
Copyright (C) 2013-2020 Aestimo group

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. http://www.gnu.org/copyleft/gpl.txt .
