Google N-grams DB
=================

This repo contains Google N-grams English One Million as a SQLite database.
The data take this form:
ngram TAB year TAB match_count TAB volume_count NEWLINE

This data is based on [Google English One Million 1-grams version 20090715](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html)
Google N-grams is licensed under [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/).
These files have been modified by taking only English One Million 1-grams that are entirely made of the letters A-Z (eg no punctuation or numbers, no accents or non-English characters).
