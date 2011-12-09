# md2html

My humble tool for converting Markdown files to nicely formatted HTML files without fuss. These can be nicer to use and share than plain text.

Run it using

    ./md2html README.md

md2html will create a file called *README.md.auto.html*.

## Features

- Easy-to-use commandline call. Can be used, e.g. in conjuction with a file monitor, a script, or a Quicksilver action.
- One-file HTML output that displays on any computer.
- Preserves the original Markdown source in the generated file.
- Simple, pretty CSS. This is taken from [toland](https://github.com/toland/)'s [QLMarkdown](https://github.com/toland/qlmarkdown), although [most commits to the stylesheet](https://github.com/toland/qlmarkdown/blame/master/styles.css) seem to be by [jiho](https://github.com/jiho). Most of it seems to based on from ``ADC'', presumably the [Apple Developer Connection](http://developer.apple.com/). As required by the QLMarkdown license, credits are included at the bottom.

## Dependencies

- [Markdown](http://daringfireball.net/projects/markdown/), of course.

## TODO

- Compile the HTML file from the source portion in-place. This is a bit tricky because the file is commonly being edited at the same time. Some editors don't handle this well.

## Use with Quicksilver

Create an Applescript file at "/Users/lgarron/Library/Application Support/Quicksilver/Actions/Markdown to HTML.scpt" with the code

    on open theFile
    	set the_file to POSIX path of theFile
    	do shell script "[your path md2html] \"" & the_file & "\""
    	return null
    end open

Make sure that your reference tomarkdown in md2html does not depend on parts of he PATH that are only available in the commandline shell.

## Credits
This product includes software developed by David Loren Parsons <http://www.pell.portland.or.us/~orc>