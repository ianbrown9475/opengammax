# OpenGammaX

This is a continuation of the OpenGamma project by Marcelo Maduar with his permission. It is for gamma ray (radiation) spectroscopy and isotope identification. It accepts output files from several types of MCA's. Real time input will be added.

## Requirements

* QT 4
  * [AUR](https://aur.archlinux.org/packages/qt4/)
* QWT 6 for QT 4
  * [AUR](https://aur.archlinux.org/packages/qwt-qt4/)
* GNU Scientific Library (GSL) version 1
  * [FTP](https://ftp.gnu.org/gnu/gsl/)

## Installation

### Compile opengammamathfuncs

1. Navigate to [`opengammamathfuncs`](./opengammamathfuncs/) and open [`opengammamathfuncs.pro`](./opengammamathfuncs/opengammamathfuncs.pro)
   in a text editor

2. Modify `GSL_ROOT` and `GSL_LIB` so that the `libgsl.so` and `libgslcblas.so` shared libraries are included. The
   default configuration assumes that a GSL 1.16 instance exists in `../gsl-1.16/` relative to `opengammax/`. 

3. Generate the makefile. Make sure that the instance of `qmake` used for this step is for QT 4. Your executable make
   have a different name.

   ```sh
   qmake-qt4 opengammamathfuncs.pro
   ```

4. Compile the code.
   ```sh
   make
   make clean
   ```

### Compile opengammax
1. Navigate to [`build`](./build/) and open [`opengammax.pro`](./build/opengammax.pro) in a text editor

2. Make sure `QT_INCLUDEPATH` points to the location of QT 4 C header files and `QWT_INCLUDEPATH` points to the location
   of QWT 6 header files.

3. Ensure that `QWT_LIB` is the shared library for QWT 6.

4. Repeat any changes in configuration for `GSL_LIB` and `GSL_ROOT`

5. Generate the makefile.

   ```sh
   qmake-qt4 opengammax.pro
   ```

6. Compile the code.
   ```sh
   make
   make clean
   ```

## Running the program

Execute the shell script [`build/ogx.sh`](./build/ogx.sh)
