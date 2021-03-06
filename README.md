#historian

Historian is a simple command line utility for storing strings or blocks of UTF8 encoded text. Think of it as a semi-manually managed non-volatile multi-buffer pasteboard for your terminal.

![historian](http://mtambo.com/historianjs.png)

**Features**

- multiple pasteboard support
- supports unix piping for adding text
- output can be by line or in its entirety
- aliases can be set for quick access when 
  another pasteboard is active

  **Installation**

  Historian works best when installed as a global module:

  `npm -g install historian`

  On installation, Historian comes with one pasteboard titled `pasteboard`.

  Historian currently relies on the default relative locations of the conf and var directories installed with the module. This will probably be changed in a future release to improve usability.


  **Usage**

  Historian's usage and arguments can be invoked by running:

  `hijs --usage`

  To list the current pasteboards available for use:

  `hijs -l`

![hijs ls](https://github.com/st-luke/node-historian/raw/master/img/hijs_ls.png)

  To create or use a pasteboard:

  `hijs -u [name]`

  Newly created pasteboards are not created on disk until data is added. If you switch to another pasteboard, the current will be disregarded if it has no contents. 

  You can examine details about the active pasteboard by running:

  `hijs -e`

![hijs -e](https://github.com/st-luke/node-historian/raw/master/img/hijs_e.png)

  This will return the name, total entries, and total characters. 

  Adding to a pasteboard is easy:

  `hijs -a string`

  You can also use the output from something else:

  `echo 'I need to remember this!!' | hijs`

or maybe a log:

![hijs piping](https://github.com/st-luke/node-historian/raw/master/img/hijs_pipe.png)

  You can output the whole pasteboard with:

  `hijs -p`

  or a specific line:

  `hijs -p 10`

  You can also assign aliases to certain strings for easy access. These are stored independently of historian's other pasteboards:

  `hijs --alias alias_name striiiing`

  You paste aliases with:

  `hijs -p alias_name`

  Or you can get a little fancier if you're doing something like running multiple dev instances or whatever I don't know:

![hijs alias piping](https://github.com/st-luke/node-historian/raw/master/img/hijs_alias.png)

The front end source will end up in the pasteboard:

  `hijs -p`

![hijs ls](https://github.com/st-luke/node-historian/raw/master/img/hijs_alias_output.png)

###License: MIT


*Readme art by Bobby Fasel*
