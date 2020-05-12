### Using man Pages:

* `man` pages are broken into sections
  * Use `man man` to see list of section numbers and the data they hold
  * In the upper-left corner of a man page, it shows the title and section number
* The "Synopsis" section of man pages shows command syntax
  * Anything between '[]' means it's optional for command operation
  * A trailing '...' means that part of the command can be specified multiple times 
* There is an "Examples" section near the bottom of man pages in most cases
* Use the `apropos` or `man -k` commands to search for man pages using a keyword
  * The `mandb` command can be used to rebuild the `man` database, which `apropos` searches
