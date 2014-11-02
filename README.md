Google N-grams DB
=================

This repo contains Google N-grams English One Million as a SQLite database.
These fields are availble:

* ngram
* year
* match_count
* page_count
* volume_count

This data is based on [Google English One Million 1-grams version 20090715](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html)
Google N-grams is licensed under [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/).
These files have been modified by taking only English One Million 1-grams that are entirely made of the letters A-Z (eg no punctuation or numbers, no accents or non-English characters).
These ngrams have been put into a SQLite database, making queries like these easy:

```sql
-- get counts of matches by ngram for appearances after 1990
SELECT ngram,SUM(match_count) AS sum_match_count FROM eng_1m_ascii WHERE year > 1990 GROUP BY ngram;
-- get a count of all matches by year
SELECT year,SUM(match_count) AS sum_match_count FROM eng_1m_ascii GROUP BY year;
```

How To
======

The directory output_eng_1m_ascii.sqlite.7z/ contains split files that can be concatenated 
to make eng_1m_ascii.sqlite.7z, which can be unarchived to make eng_1m_ascii.sqlite,
which is a SQLite database.

```bash
# concatenate the split files under output_eng_1m_ascii.sqlite.7z/
cat $( find output_eng_1m_ascii.sqlite.7z/ -type f | sort ) > eng_1m_ascii.sqlite.7z 
# unarchive the 7zip file to get the SQLite database
7z x eng_1m_ascii.sqlite.7z
# use the SQLite database
sqlite3 eng_1m_ascii.sqlite.7z
```
