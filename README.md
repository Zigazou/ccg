Crude Call Graph for PHP
========================

`ccg` is a very simple and crude call graph generator. It takes one PHP file and
outputs the graph using the dot language (from GraphViz).

It is able to ignore either or both PHP function and Drupal 7 core function (these
functions are hard written in the body of `ccg`).

Requirements
------------

Here are the requirements:

- **PHP >= 5.3, CLI version**: outputs the call graph as a DOT file
- **GraphViz (optional)**: using the `dot` command, generates an image
- **Image Magick (optional)**: using the `display` command, displays the graph

Install
-------

Copy the `ccg` script in a directory pointed to by the `PATH` environment
variable. Make sure the script has executable rights.

That’s all!

Example
-------

Takes a PHP source file and displays its call graph:

    ccg file.php | dot -Tpng | display

Takes a PHP source file and displays its call graph, ignoring any call to a known
PHP function:

    ccg -ip file.php | dot -Tpng | display

Takes a PHP source file and displays its call graph, ignoring any call to a known
Drupal 7 core function:

    ccg -id file.php | dot -Tpng | display

Takes a PHP source file and displays its call graph, ignoring any call to a known
Drupal 7 core function or PHP function:

    ccg -idp file.php | dot -Tpng | display
