*******
repchar
*******

This is a simple command line script that creates a list of all
characters contained in a given document.

Usage
=====

repchar [-h] -o OUTFILENAME [-v] [-c] INFILENAME

positional arguments:
  INFILENAME            Filename

optional arguments:
  -h, --help            show this help message and exit
  -o OUTFILENAME, --outfile OUTFILENAME, --out OUTFILENAME
                        Filename for report
  -v, --verbose         Set log level to INFO.
  --version             show program's version number and exit
  -c, --comb, --combining
                        Create special report for combining characters

Module
======

You can also use the ``CharReporter`` class in your own code:

.. code:: python

    >>> from repchar import CharReporter
    >>> s = u"ABCD"
    >>> r = CharReporter()
    >>> r.feed(s)
    >>> r.report()
    chr	hex	count	unicode
    A	0041	1	LATIN CAPITAL LETTER A
    B	0042	1	LATIN CAPITAL LETTER B
    C	0043	1	LATIN CAPITAL LETTER C
    D	0044	1	LATIN CAPITAL LETTER D

The count of each letter is stored in ``CharReporter.chars``:

.. code:: python

    >>> r.chars
    {u'A': 1, u'C': 1, u'B': 1, u'D': 1}

