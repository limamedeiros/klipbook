# Klipbook

Klipbook collates highlights and notes that you've created on your Kindle into a nice html file.

## An example of a clippings file generated by Klipbook

<img src="https://github.com/grassdog/klipbook/raw/master/example.png" alt="Example of a clippings file" />

## What sources does it support?

Klipbook can take your highlights from a clippings file off a physical Kindle device
or from the [Kindle highlights site](https://kindle.amazon.com/your_highlights) itself.

## When should I use the file and when should I use the site?

If your books are purchased from Amazon directly then use the site. The site is the
canonical source and will contain all of your notes and highlights from across all of 
your Kindle devices and applications. Currently the Amazon highlights site only shows
clippings for books you've purchased on Amazon.

If your books are personal documents and you've read them on your Kindle device
itself then you should use the file from that device as a source i.e. your Kindle
device only keeps clippings that you made directly on it.

## How does it work?

Klipbook supports two main commands: `collate` and `list`.

### Collate

`collate` pulls together the clippings from your latest annotated book and combines them
into a simple html file.

#### From a file

Copy your clippings file (called "My Clippings.txt" on a 3rd generation Kindle) from your Kindle device to your local drive via USB.

Then write out a list of your clippings via:

    $ klipbook collate "file:My Clippings.txt"

This command will write the collected clippings for the latest annotated book to a file in the current
directory. You can override the output directory with the `--output-dir` switch.

You can also specify a maximum count of books you'd like collated with the `--num-books` switch.

Klipbook will not overwrite an exiting file by default. You can change this with
the `--force` flag.

#### From the site

Specify your Amazon username and password to klipbook and it will scrape the site and
output a clippings file.

    $ klipbook collate site:my-username@blah.com:my-password
    
The same flags above apply.

Note that the scraping requires a network connection (obviously) and can take a while
so please be patient.

### Set up defaults

If you don't feel like having your Amazon credentials in your shell history you can set your
default source in the klipbook rc file: `~/.klipbookrc`.

This is simply a YAML file and you can specify default values for the source and the
output directory, e.g.

    $ cat ~/.klipbookrc
    source: site:my-username@blah.com:my-password
    output: my/default/output/directory

Command line options override the defaults stored in the rc file.

### List

The list command lists the books avaiable in the specified source.

    $ klipbook list file:"My Clippings.txt"

    Book list:
    [1] The Big Sleep by Raymond Chandler
    [2] How to jump out of a plane without a parachute and survive by Rip Rockjaw

By default it will only list the latest book. This can be overrided with the
`--num-books` switch.

## Installation

Klipbook is a Ruby gem. To install simply run:

    gem install klipbook

## Supported Devices

Klipbook has been tested on clippings files from 3rd generation Kindles and the Kindle Touch.

## Tested platforms

Klipbook has been tested on Mac OSX Mountain Lion using MRI 1.9.3. 

## Contributing to Klipbook

Fork the project on [Github](https://github.com/grassdog/klipbook), add tests for your changes, and submit a well described pull request. 

## Copyright

Copyright (c) 2013 Ray Grasso. See LICENSE.txt for further details.

