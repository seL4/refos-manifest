RefOS
=====

RefOS is a sample implementation of a simple multi-server OS on seL4.

The aim of RefOS is to:

* Provide reference design of a simple multi-server OS protocol on seL4.
* Provide a sample implementation of the protocol.
* Simplify development & porting of userland programs.
* Serve as an example codebase to start new component-based seL4 projects.

#### Features

* Simple and light-weight OS.
* Multi-server component based OS design.
* Process & thread abstraction.
* Dataspace abstraction.
* Shared memory support.
* Dynamic mmap and sbrk support.
* User-land serial & timer drivers.
* Well documented, Doxygen supported.

**NOTE:** Please note that RefOS is intended to be only an example system, a work-in-progress, and is not to be
deployed as a real OS solution. RefOS is not verified, not high assurance, and may not be optimised for speed and
efficiency, and may be missing most of the features you'll expect in a deployable OS environment.

### Quick Start

#### Building RefOS

In order to build the RefOS implementation codebase:

1. Read: http://sel4.systems/Download/. Set up the environment (repo tool, cross compilers...etc) as per the 
   instructions on the page.

3. > repo init -u ssh://git@github.com/seL4/refos-manifest -b master

4. > repo sync

5. Install the following packages (package named based on Ubuntu 14.04):
  > sudo apt-get install python-tempita

6. > make help (to list the configs)

7. > make \<config\>

   > make silentoldconfig

   Where <config> is one of the configurations listed with the above command,
   eg. make kzm\_debug\_test\_defconfig

8. > make

  If all goes well you should now have a bootable system image (refos/images/refos-image).

9. > make simulate-kzm

  Look under http://sel4.systems/Download/ section "Simulating the result".


#### Building Design Document

Note that the design document has not been finished yet, and is still a work-in-progress. Thus, some
details may slightly differ between the design document and the implementation.

In order to build the design document PDF file:

1. Clone the repository (see above, Building RefOS).

3. Install the following packages (package named based on Ubuntu 14.04):
  > sudo apt-get install texlive-latex-base mscgen texlive-latex-extra texlive-fonts-recommended

4. > make design

   This should give you a path to the paper.pdf document.
   

#### Building Doxygen Code Documentation

1. Clone the repository (see above, Building RefOS).

2. Install the following packages (package named based on Ubuntu 14.04):
  > sudo apt-get install doxygen

3. > cd docs/

4. > make

License
-------

The files in this repository are released under standard open source
licenses. RefOS code is released under the BSD license where possible, and GPL for some
external software. Please see the individual file headers and
[`LICENSE_BSD2.txt`](LICENSE_BSD2.txt) for details.

Please note that RefOS is intended to be sample code and is not high assurance software.
We are not reponsible for any consequences if you choose to deploy this software in
production.
