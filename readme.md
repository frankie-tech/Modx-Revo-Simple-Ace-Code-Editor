
# Modx Extra: Simple Ace Code Editor

This is a [MODX Revolution](https://modx.com) extra.

It integrates [Ace Code Editor](https://ace.c9.io) into MODx Revolution in a simple way.

It is available as a package in MODX Extra repository: https://modx.com/extras/package/simpleacecodeeditor

## Features

 * Dead simple. Really.
 * Works out of the box with sensible default
 * CTRL-D to duplicate
 * Autocompletion on CTRL-SPACE
 * MODX tag highlighting
 * Set a specific MIME type for you chunks (like a shebang)
   E.g. text/x-sass to have SASS syntax highlighting

## Install

It is recommanded to install from MODX Extra repository (see link above).

You can also upload manually the transport package (found in `_dist` folder) to your MODX installation.

## Plugin properties

The plugin offers several useful properties.

Note that it is recommended to create a new Property Set instead of editing the default one.
**AcePath**: URL or path to ACE javascript file

*default: `https://cdnjs.cloudflare.com/ajax/libs/ace/1.3.1/ace.js`*

**Theme**: editor theme name (you can test them all here: https://ace.c9.io/build/kitchen-sink.html)

Bright themes: `chrome`, `clouds`, `crimson_editor`, `dawn`, `dreamweaver`, `eclipse`, `github`, `iplastic`, `solarized_light`, `textmate`, `tomorrow`, `xcode`, `kuroir`, `katzenmilch`, `sqlserver`

Dark themes: `ambiance`, `chaos`, `clouds_midnight`, `dracula`, `cobalt`, `gruvbox`, `gob`, `idle_fingers`, `kr_theme`, `merbivore`, `merbivore_soft`, `mono_industrial`, `monokai`, `pastel_on_dark`, `solarized_dark`, `terminal`, `tomorrow_night`, `tomorrow_night_blue`, `tomorrow_night_bright`, `tomorrow_night_eighties`, `twilight`, `vibrant_ink`

*default: `monokai`*

**ReplaceCTRLDKbdShortcut**: Replace the CTRL-D (or CMD-D) keyboard shortcut to perform a more sensible action, which is to duplicate the current line or selection (instead of deleting, which is the default behavior)

*default: `true`*

**Autocompletion**: Enable Autocompletion: none, basic (show on CTRL-Space) or live (show on typing).
Note that "ext-language_tools.js" must be available alongside ace.js

*default: `basic`*

**SettingsMenu**: Add a settings menu accessible with CTR-Q (or CMD-Q)

Note that "ext-settings_menu.js" must be available alongside ace.js
  
*default: `false`*

**Spellcheck**: Enable spellcheck

Note that "ext-spellcheck.js" must be available alongside ace.js

*default: `false`*

**Emmet**: Enable emmet

Note that "ext-emmet.js" must be available alongside ace.js
   
*default: `false`*

**ChunkDetectMIMEShebang**: Enable 'shebang-style' MIME detection for chunks (in description or in the first line of chunk content).

This is particularly useful if your chunk contains directly JS, or SASS, or anything different than HTML...

See chapter "MIME detection for Chunks" below.

*default: `true`*



## MIME detection for Chunks

By default, chunk are HTML and they are highlighted as such. However, you could want to store other type of data in a chunk, and want to have proper highlighting. For example, you could want to store directly Javascript code, or SASS, or LESS, etc...

The property _ChunkDetectMIMEShebang_ (enabled by default) will let you specify, if needed, a specific MIME type to highligh your chunk with.

Detected MIME values are `text/x-smarty`, `text/html`, `application/xhtml+xml`, `text/css`, `text/x-scss`, `text/x-sass`, `text/x-less`, `image/svg+xml`, `application/xml`, `text/xml`, `text/javascript`, `application/javascript`, `application/json`, `text/x-php`, `application/x-php`, `text/x-sql`, `text/x-markdown`, `text/plain`, `text/x-twig`

The examples below are for a chunk that is used for storing [SASS](https://sass-lang.com) content (corresponding type is `text/x-sass` or `text/x-scss`).


__You can specify this value directly in your chunk, on the first line (usually inside a comment):__

![](https://user-images.githubusercontent.com/7137528/39598106-c3b611ec-4f17-11e8-9869-12f1f705a099.png "MIME type in chunk's content")


__Or you can specify this value in the chunk's description.__

![](https://user-images.githubusercontent.com/7137528/39598124-cf5e1878-4f17-11e8-88ea-adeb3441f95c.png "MIME type in chunk's description")

