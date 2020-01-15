# OpenGammaX

This is a continuation of the OpenGamma project by Marcelo Maduar with his permission. It is for gamma ray (radiation) spectroscopy and isotope identification. It accepts output files from several types of MCA's. Real time input will be added.

## Installation

### Compile opengammamathfuncs

1. Navigate to [`opengammamathfuncs`](./opengammamathfuncs/) and open [`opengammamathfuncs.pro`](./opengammamathfuncs/opengammamathfuncs.pro)
   in a text editor

2. Version 1 of the [GNU Scientific Library (GSL)](https://www.gnu.org/software/gsl/) is required. Modify `GSL_ROOT`
   and `GSL_LIB` so that the `libgsl.so` and `libgslcblas.so` shared libraries are included. The default configuration
   assumes that a GSL 1.16 instance exists in `../gsl-1.16/` relative to `opengammax/`. 

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

2. This project uses QT 4 and QWT 6. Make sure `QT_INCLUDEPATH` points to the location of QT C header files and
   `QWT_INCLUDEPATH` points to the location of QWT header files.

3. Ensure that `QWT_LIB` is the shared library for QWT.

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
