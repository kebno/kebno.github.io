---
layout: post
title: Zotero Makes References Easy
---

I use [Zotero](http://www.zotero.org) to manage references for my research.
It supports BibTeX export; great for writing papers in LaTeX.

Today, I learned that Zotero features reference drag-and-drop (they call it
[Quick Copy](https://www.zotero.org/support/creating_bibliographies)).
Select a document
in Zotero, click and drag it to any text area, and like magic, you now have a
have a full reference in the format of your choosing.

### Tidy the Quick Copy Reference 

The Quick Copy BibTeX reference will often include a long entry for the locally
stored version of the document. For me, and probably for you too, there is no
need to share that local file location.  You can remove it easily from the
reference using standard Unix tools (e.g. `sed`, `perl`). 

However, I write in Vim and can use its built-in commands to search for and
delete every unwanted entry.  The following does the trick, prompting you for
each removal: `:%s/,\n\s*file = {.*}//gc`.

To explain, it is the substitude command (`:s`), in the current buffer (`:%s`),
searching for a comma then newline then whitespace (`,\n\s*`), then the text
"`file = `", and finally, the curly braces and any characters in-between
(`{.*}`). The trailing `gc` means replace all occurences in each line (`g`),
and confirm each substitution (`c`). 

For more information on the substitute command, read the Vim help files by
typing `:help substitute` and `:help s_flags`. 
