Information Management for Journalists
======================================

Introducing data
----------------

* Types of data:
    * Simple types
        * Numbers (bytes, ints, floats)
        * Text (chars, strings)
        * Boolean
        * Enumerations
        * Binary blobs (images, audio)
    * Complex types
        * Lists (1D)
        * Tables (2D)
        * Relationships (3 or more dimensions)
        * Objects (hierarchical data)
* Metadata:
    * Unique ids
    * Constraints ("business rules")


Storing data
------------

* Lists: Plain text
* Tables: Spreadsheets (CSV, Excel, Google Docs)
* Relationships: SQL Databases (MySQL, PostgreSQL, sqlite)
* Objects: Flat-files (JSON, YAML) or Object Databases (MongoDB, CouchDB)


Tracking changes
----------------

* What constitutes a change in version?
* The timestamp: atomic unit of change
* Sometimes it makes sense to record that things don't change too
* Files and folders (a.k.a naming things)
    * Always name from less specific to more specific
    * Always timestamp things you're changing
    * Always make copies (you have unlimited hard drive space--use it)
* Dropbox: The poor man's version control
* git: The engineer's version control
    * git in 5 minutes
    * Commit messages matter
    * Works for text formats (CSV, flat files), but not for binaries
    * Not designed for big data
* Change tables and data warehouses: creating problems to solve problems


Data pipelines
--------------

* Why repeatable processes?
    * Ensure clear provenance of the data
    * Depend against attacks on integrity
    * Self-documenting workflow
    * Show your work
* Acquisition
    * Ways to get data
        * Curl
        * APIs
        * Scrapers
        * PDF / OCR
    * Documenting provenance
* Processing
    * Scripts
        * Bash scripts
        * csvkit
        * Python
    * Documenting order of operations
    * Documenting your code
    * Naming things; revisited
* Testing
    * Test assertions about the data
    * Test novel derived facts
* Shims, adapters and glue code
* Crons

