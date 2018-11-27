Hack to check answers for NYTimes Spelling Bee Game.

1) Clone this repository
2) Convert line endings to UNIX style with `sed`: `sed -i.bak 's/\r$//' words_alpha.txt` See: https://askubuntu.com/questions/803162/how-to-change-windows-line-ending-to-unix-version
3) `grep` the file:

`cat words_alpha.txt | grep -x '.\{4,\}' | grep -Eo "^[UuDGMOPRdgmopr]*[Uu]+[UuDGMOPRdgmopr]*$"`

Where the first `grep` command filters min word length of four.
Second `grep` command searches for lines matching the pattern:
- 0 or more entries of all allowable letters.
- At least one entry of the required letter.
- 0 or more entries of all alllowable letters.

english-words
=============

A text file containing over 466k English words.

While searching for a list of english words (for an auto-complete tutorial)
I found: http://stackoverflow.com/questions/2213607/how-to-get-english-language-word-database which refers to ~~http://www.infochimps.com/datasets/word-list-350000-simple-english-words-excel-readable~~ (link no longer available).

No idea why infochimps put the word list inside an excel (.xls) file.

I pulled out the words into a simple new-line-delimited text file.
Which is more useful when building apps or importing into databases etc.

Copyright still belongs to them.

Files you may be interested in:

-  [words.txt](words.txt) contains all words.
-  [words_alpha.txt](words_alpha.txt) contains only [[:alpha:]] words. If you want a quick solution choose this.
-  [words_dictionary.json](words_dictionary.json) contains all the words from words_alpha.txt as json format. 
If you are using Python, you can easily load this file and use as a dictionary for faster performance. All the words are assigned with 1 in the dictionary.
See [read_english_dictionary.py](read_english_dictionary.py) for example usage.

