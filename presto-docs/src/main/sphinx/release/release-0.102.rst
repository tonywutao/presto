=============
Release 0.102
=============

Unicode Support
---------------

All string functions have been updated to support Unicode. The functions assume
that the string contains valid UTF-8 encoded code points. There are no explicit
checks for valid UTF-8, and the functions may return incorrect results or fail on
invalid UTF-8.  Invalid UTF-8 data can be corrected with :func:`from_utf8`.

Additionally, the functions operate on Unicode code points and not user visible
*characters* (or *grapheme clusters*).  Some languages combine multiple code points
into a single user-perceived *character*, the basic unit of a writing system for a
language, but the functions will treat each code point as a separate unit.


General Changes
---------------

* Support returning booleans as numbers in JDBC driver
* Add :func:`from_utf8` and :func:`to_utf8` functions.

Hive Changes
------------

* Collect more metrics from ``PrestoS3FileSystem``.
* Retry when seeking in ``PrestoS3FileSystem``.
* Ignore ``InvalidRange`` error in ``PrestoS3FileSystem``.
* Implement rename and delete in ``PrestoS3FileSystem``.
