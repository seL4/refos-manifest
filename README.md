<!--
     Copyright 2016, Data61, CSIRO

     SPDX-License-Identifier: CC-BY-SA-4.0
-->

RefOS - Reference Design For A Microkernel Based Operating System
=================================================================

RefOS is a sample implementation of a simple multi-server operating system built on seL4.

The aim of RefOS is to:

* Provide a reference design of a simple multi-server operating system built on seL4
* Provide a sample implementation of how seL4 protocols can be used
* Simplify development and porting of userland programs built on seL4
* Serve as an example codebase to start new component-based seL4 projects

#### Features

* Simple and light-weight operating system
* Multi-server component based design
* Process and thread abstraction
* Dataspace abstraction
* Shared memory support
* Dynamic mmap and sbrk support
* Userland serial and timer drivers
* Sample user programs include:
    * Terminal - a simple terminal program
    * Tetris - a port of Micro Tetris
    * Snake - a snake game

**NOTE:** Please note that RefOS is intended to be only an example system, a work in progress,
and is not to be deployed as a real operating system solution. RefOS is not verified, is not
high assurance, is not optimised for speed and efficiency and may be missing most of the features
one would expect in a deployable operating system environment.

### Quick Start

#### Building RefOS

In order to build RefOS's codebase:

1. Read: <https://docs.sel4.systems/projects/buildsystem/host-dependencies.html>
   Set up the environment (repo tool, cross compilers and build
   dependencies) as per the instructions on the page.

2. `repo init -u ssh://git@github.com/seL4/refos-manifest -b master`

3. `repo sync`

4. Install the following packages (package named based on Ubuntu 14.04):
   > `sudo apt-get install python-tempita`

5. make help (to list the default configurations)

6. make \<config\>, where \<config\> is one of the configurations listed with the \<make help\> command:
   eg. `make kzm\_debug\_test\_defconfig``

7. `make silentoldconfig`

8. `make`

   You should now have a bootable system image (refos/images/refos-image).


9. `make simulate-kzm` (or a different command depending on the configuration you chose, run \<make help\>
   to list the different configurations and how to run them)


#### Building The Design Document

Note that the design document has not been finished yet and is still a work in progress. Therefore, some
details may differ slightly between the design document and RefOS's implementation.

In order to build the PDF design document:

1. Clone the repository (see above).

3. Install the following packages (package named based on Ubuntu 14.04):
  > sudo apt-get install texlive-latex-base mscgen texlive-latex-extra texlive-fonts-recommended

4. `make design`

   This command builds the PDF documentation and provides a path to the document.


#### Building Doxygen Code Documentation

1. Clone the repository (see above).

2. Install the following packages (package named based on Ubuntu 14.04):
  > sudo apt-get install doxygen

3. `make docs`

5. In a web browser, open "docs/html/index.html"


No Warranty
-----------

Please note that RefOS is intended to be sample code and is not high assurance software.
We are not responsible for any consequences if you choose to deploy this software in
production.
