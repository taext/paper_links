# paper_links
UI design proposal and python tooling

<br>

## TL;DR - clickable link functionality in hard-coded media

<br>

"Imagine printer papir or a notebook that comes with a couple of qrcodes on each page for you to use, if necessary, to easily *add clickable links*."

<br>
    

paper_links combines the dynamic nature of HTML links with the physical nature of printed paper material.

paper_links accomplishes this using QR codes and link shorteners only.

Technically, it is just a Python CLI tool to create random (unused) link shortener URL QR codes.

## What's the idea?

The idea is **producing clickable link functionality for hard-coded media**.

These QR codes containing unused links can be printed now and then defined as links at a later time by
- using the link shortener provider's own interface and 
- choosing the custom link option 

They are clickable links that can be physically printed now and defined later *by the user of the printed material*.

Imagine printer paper or a notebook that comes ready with a qrcode or two on each page for you to use, if necessary, to easily add clickable links.

Or in a YouTube video, on a t-shirt, in a report, or as a roll of stickers for general use.

<br>

## Installation

How to install paper_links in a [Google Colab](https://colab.research.google.com/drive/1CBx1kr00HKaCA3N7qzAQBDsQx2ENxPu9) notebook.

<br>

## Usage

Run the script with the argument `1` to get a single bit.ly link:

    $ paper_links 1

    https://bit.ly/daSjviC

Specify which provider to use by setting the argument to `True`. 

Options are `bitly`, `tinycc`, `tinyurl`, `isgd`, `soogd` and `all_urls`:

    $ paper_links --bitly=True --tinycc=True

    https://bit.ly/fZyHLbq
    https://tiny.cc/JSwnQq

Use the `--count=` argument to specify multiple results:

    $ paper_links --tinycc=True --count=3

    https://tiny.cc/Eses2F
    https://tiny.cc/CC9ba9
    https://tiny.cc/K1NtgX

Use the argument `--long_hash=True` to get longer URL hashes (to minimize collisions with existing URLs):

    $ paper_links --bitly=True --long_hash=True

    https://bit.ly/ExCLy96Uqnil      # 12 digits vs. 7 digits

Use the argument `write_qrcode=True` to write individual QR code `.png`'s and a horizontally combined `.jpg`:

    $ paper_links --bitly=True --count=3 --write_qrcode=True

    https://bit.ly/Cb3tHujtPcJS
    https://bit.ly/t7qKrdfqVpS5
    https://bit.ly/2VgHfwQZkCDa

![qrcode](horizontally_combined.jpg)

