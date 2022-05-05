# Motoron Motor Controller Python library for Raspberry Pi

[www.pololu.com](https://www.pololu.com/)

## Summary

This is a Python 3 library that helps interface with
[Motoron Motor Controllers][motoron] from a Raspberry Pi.
It should also work on other computers as long as they have Python 3, I&sup2;C
and the [smbus2] library.
This library does **not** support Python 2.

## Getting started

To use this library, you will also need to enable I&sup2;C,
set up the I&sup2;C device permissions properly
(so you do not have to use `sudo`), and connect the Motoron to your
Raspberry Pi's I&sup2;C bus.  If you are not sure how to do those things,
see the "Getting started" sections of the [Motoron user's guide][guide].

This library depends on Python 3.  To install Python 3 on Raspbian, run:

    sudo apt-get install python3-dev python3-pip

This library depends on [smbus2], which you can install by running:

    sudo pip3 install smbus2

Finally, to download and install the library, run:

    git clone https://github.com/pololu/motoron-rpi.git
    cd motoron-rpi
    sudo python3 setup.py install

## Examples

Several example programs come with the library.  They are single-file
Python programs that have names ending with `_example.py`.

You can run an example program by typing the path to the example.  For example,
if you are in the `motoron-rpi` directory, type `./simple_example.py` to run
that example.

## Classes

The main class provided by this library is motoron.MotoronI2C.

## Documentation

For complete documentation of this library, see
[the motoron-rpi documentation][doc].
If you are already on that page, then click the links in the "Classes" section
above.

## Command timeout

By default, the Motoron will turn off its motors if it has not received a valid
command in the last 1.5 seconds.  You can change the amount of time it
takes for the Motoron to time out using
motoron.MotoronI2C.set_command_timeout_milliseconds or you can disable the
feature using motoron.MotoronI2C.disable_command_timeout.

## Version history

* 1.0.0 (2022-05-13): Original release.

[doc]: https://pololu.github.io/motoron-rpi/
[guide]: https://www.pololu.com/docs/0J84
[smbus2]: https://pypi.org/project/smbus2/
[motoron]: https://pololu.com/motoron
