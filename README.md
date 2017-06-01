# Instruction Error Analysis using SHVAL

This repo is a fork of https://github.com/lam2mo/shval that performs:
* Error evolution analysis per memory location.
* Error evolution analysis per instruction.
* Isolating error caused by functions.

Note: This fork disables MPFR shadow value analysis.

## Instructions

Currently this project only works on x86\_64 Linux.

Dependencies:

* [Intel Pin 3.2](https://software.intel.com/en-us/articles/pintool-downloads)
  (Tested version: 81205)

  Set the `PIN_ROOT` variable in the `./build.sh` script.

	Copy pin_isa.H to `PIN_ROOT/source/include/pin/`

To build all tools, use the `./build.sh` command in the `tools` directory. To
run a tool, use a command similar to the following:

    pin -t /path/to/obj-intel64/shval-native32.so -- /path/to/app

This assumes that the `pin` wrapper is in your `PATH`. Application parameters
can be included at the end if necessary. In addition, most tools provide various
command-line options to customize their runtime behavior. To see descriptions of
each tool's options, run the tool without an app. These options must be
specified after the tool library but before the `--` separator.

## Authors

SHVAL was originally written by Michael O. Lam, lam26@llnl.gov. This fork is
written by Ramy Medhat, rmedhat@uwaterloo.ca.
