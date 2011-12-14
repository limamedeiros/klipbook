# Klipbook

Klipbook creates a html summary of your Kindle book clippings.

## How does it work?

Copy your clippings file (called "My Clippings.txt" on a 3rd generation Kindle) from your Kindle device to your local drive via USB.

**List the books in your clippings file:**

    $ klipbook list "My Clippings.txt"

    The list of books in your clippings file:
    [1] The Big Sleep by Raymond Chandler
    [2] How to jump out of a plane without a parachute and survive by Rip Rockjaw

**Print a html summary for the book of your choice:**

Choose the index of the book you are interested in and print a html summary with the `summarise` command:

    $ klipbook summarise "My Clippings.txt" 1 big-sleep-clippings.html

Keep this nicely formatted html version of your clippings for your own reference.

## Example of a summary file generated by Klipbook

<img src="https://github.com/grassdog/klipbook/raw/master/example.png" alt="Example of a summary file" />

## Installation

Klipbook is a Ruby gem. To install simply run:

    gem install klipbook

## Why not just see your clippings on the Amazon site?

Currently [the Amazon highlights site](https://kindle.amazon.com/your_highlights) only shows clippings for books you purchased on Amazon.

## Tested platforms

Klipbook has been tested on MRI 1.9.3 on Mac OSX.

## Contributing to Klipbook

Fork the project on [Github](https://github.com/grassdog/klipbook) and submit a pull request. 

## Copyright

Copyright (c) 2011 Ray Grasso. See LICENSE.txt for further details.

