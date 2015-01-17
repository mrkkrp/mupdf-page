# Script to remember page when you quite MUPDF

This is a tiny shell script that allows MUPDF (semi-) automatically remember
page that is opened when you close it. It does so by keeping directory
`~/.cache/mupdf/`, where it creates files whose names correspond to names of
PDF files you visit. When you open a PDF file via this script it searches
for corresponding file and reads page number form it. Then it invokes MUPDF
and takes care of the rest. When you quit MUPDF it asks you for page number
to remember. You can enter page number or cancel this query altogether, so
page number for this file will not be changed.

Tip: use `P` command to find out page number (I can be different from number
that is displayed on document's footer).

## Installation

Copy file `pdf` into directory that is in your `PATH` environment
variable. I strongly recommend using of `~/bin/` directory for this sort of
scripts.

Create `~/bin/` directory if it doesn't exist already. Copy file `pdf` into
it and change file mode, so you can execute it:

```
$ cd bin
$ chmod 755 pdf
```

If you have never used `~/bin` directory for your custom scripts, add the
following to your `.bashrc` file:

```
export PATH=$PATH:$HOME/bin
```

Install `zenity` and `xdotool` using repositories of your GNU/Linux
distribution.

Now you can use `pdf` command to open PDF files from shell. You can also
associate `pdf` command with PDF files via your desktop environment so when
you open PDF files from within file manager this script will be used.

## License

Copyright (c) 2014 Mark Karpov

Distributed under GNU GPL, version 3.
