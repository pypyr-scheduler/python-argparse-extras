# python-argparse-extras

Some helpers for python's argparse.

Currently, this package provides 3 HelpFormatter classes that you can extend and / or use with
python's `argparse` module:

## Contents

### `formatter.WideHelpFormatter`

HelpFormatter which tries to use a given amount of the terminal width.

The maximum line length is determines by the class attribute `percentage_of_line_length`.
This defaults to the full width (1.0). Override this class and set your own percentage.

This uses ``shutil.get_terminal_size()`` to determine the line length.

### `formatter.ThreeQuarterWidthHelpFormatter`

A `WideHelpFormatter` subclass with its `percentage_of_line_length` set to three quarters of the terminal line length.

### `formatter.ThreeQuarterWidthDefaultsHelpFormatter`

A `ThreeQuarterWidthHelpFormatter` subclass which also derives from `argparse.ArgumentDefaultsHelpFormatter`. This means that in addition to using 3/4 of the terminal line length, it also prints the argument defaults in the help text.

## Installation & Usage

Install the package with your favourite python package manager:

    pip install apextras

or directly into your [pipenv](https://pipenv.readthedocs.io/):

    pipenv install apextras

After that, you can use these classes in the same way as any other `argparse.HelpFormatter` subclass while creating your argument parser:

    from apextras.formatter import WideHelpFormatter
    parser = argparse.ArgumentParser(formatter_class=WideHelpFormatter)
    parser.add_argument(...)
    ...
