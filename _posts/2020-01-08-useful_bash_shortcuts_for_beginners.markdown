---
layout: post
title: Useful BASH Shortcuts for Beginners
date:   2020-01-08 18:00 +0630
image:  Bash-logo.jpg
tags:   [Guide, BASH]
---

# Useful BASH Shortcuts for Beginners
By default, BASH is default for most Linux distributions. BASH shell provides keyboard shortcuts for better interaction for users. So, let's start now.

## Moving Cursor

- `Ctrl+A` or  `HOME` - moves cursor to the start of the line
- `Ctrl+E` or `END` - moves cursor to the end of the line
- `Ctrl+B` or `Left Arrow` - moves cursor back for one character
- `Ctrl+F` or `Right Arrow` - moves cursor forward for one character
- `Ctrl+Left Arrow` or `Alt+B`or `Esc+B` - moves cursor back for one word
- `Ctrl+Right Arrow` or `Alt+C` or `Esc+F` - moves cursor forward for one word

## Deleting Text

- `Ctrl+H` or `BACKSPACE` - removes the character before the cursor
- `Ctrl+D` or `DELETE` - removes the character under the cursor
- `Ctrl+K` - removes all text from the cursor to the end of the line
- `Ctrl+U` - removes all text from the cursor to the start of the line
- `Ctrl+W` - removes the word before the cursor
- `Alt+D` - removes the word forward the cursor

![Image Source - Twitter]({{site.baseurl}}/img/Bash-shortcuts.jpeg)

## Searching BASH History

- `Up Arrow` - gets previous entered command (multiple `Up Arrow` results prior entered command)
-  `Ctrl+R` - search BASH history in reverse, type character you want to find in the history
-  `Ctrl+S` - search BASH history in forward, type character you want to find in the history

## Cutting and Pasting
 - `Ctrl+W` - cuts the word before the cursor to clipboard
 - `Ctrl+K` - cuts the part of the line forward the cursor to clipboard
 - `Ctrl+U` - cuts the part of the line before the cursor to clipboard
 - `Ctrl+Y` - paste the last thing you cut from clipboard

## Working with Processes

- `Ctrl+Z` - suspend current foreground process, same as sending **SIGSTOP** or 19 to process
- `Ctrl+C` - interrupt current foreground process, same as sending **SIGINT** or 2 to process
- `Ctrl+D` or `exit` - exit current BASH shell

## Dealing with Typos

- `Ctrl+T` - transposes the character before the cursor with the character under the cursor
- `Alt+T` -  transposes the current word with previous word
- 

## BASH Bang(!) Command

- `!!` - executes previous command
- `!top` - executes recent command that starts with 'top'
- `!$` or `Alt+.` - executes last word of previous command
- `!*` - displays last word of previous command

## TAB Completion

TAB Completion is a very useful feature provided by BASH shell. **File, directory, and command name** are automatically completed if possible with the press on `TAB` key.

---

These are not all BASH shortcuts. Leave comment below and let me know if there is something new shortcuts, I would rather add here on this post. To conclude, cramming all BASH shortcuts is not necessary in our daily terminal usage. But mastering with some shortcuts is indeed useful.

Peace Out!!!

---

