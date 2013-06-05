# Information Management for Journalists

## Introducing data

### Chapter 1: Simple (primitive) data types

* Self-introduction
* What is information management?
    * The ways that we organize and structure information for analysis and retrieval.
* Course goals
* Caveat: the nature of a survey course

An overview of various types of data, with a cursory look into how each is stored by the computer. Each type will be illustrate with examples from a variety of applications (Excel, Python, etc).

* Numbers (bytes, ints, uints, floats)
* Text (chars, strings)
* Boolean
* Enumerations
* Binary blobs (images, audio)

### Chapter 2: complex data types

Delving deeper into types by analyzing how they can be combined together to form complex data types. We will discuss the various these types may be serialized (JSON, XML, etc). 

* Lists (1D)
* Tables (2D)
* Relationships (3 or more dimensions)
* Maps / hashes / key-value pairs...
* ...objects (nested data)

### Chapter 3: metadata

Types of data that document how your data works. Illustrate types with both examples and counterexamples.

* Explicit (database schemas) v. implicit (column definitions)
* Unique ids
* Foreign keys
* Constraints ("business rules")
* Text encodings (ascii, unicode, latin-1)


## Storing data

### Chapter 4: storing simple datasets

Survey the available methods for storing simple lists and tables. Discuss what primitive types are supported by different formats.

* Lists: Plain text
* Tables: Spreadsheets (CSV, Excel, Google Docs)

### Chapter 5: storing complex datasets 

Discuss ways of storing multi-table or nested data. Briefly explore the universe of databases and how they are relevant to different applications.

* Relationships: SQL Databases (MySQL, PostgreSQL, sqlite)
* Flat (serialized) objects: JSON, XML, YAML
* Object Databases MongoDB, CouchDB
* Search-oriented: PANDA
* Big data: Hadoop


## Tracking changes

### Chapter 6: Understanding versions

* What constitutes a change in version?
    * Data cleanup
    * Derived values
    * Processing: Excel, Refine, scripts, etc.
* The timestamp: atomic unit of change
* Sometimes it makes sense to record that things don't change too
* Files and folders (a.k.a naming things)
    * Always name from less specific to more specific
    * Always timestamp things you're changing
    * Always make copies (you have unlimited hard drive space--use it)

### Chapter 7: Versioning tech

* Dropbox: The poor man's version control
* git: The engineer's version control
    * git in 5 minutes
    * Commit messages matter
    * Works for text formats (CSV, flat files), but not for binaries
    * Not designed for big data
* Change tables and data warehouses: creating problems to solve problems


## Data pipelines

### Chapter 8: Repeatable processes

* Answering questions with data
* Ensuring provenance of the data
* Depend against attacks on integrity
* Self-documenting workflow
* Show your work

### Chapter 9: Data acquisition

* Where to find data
    * Government portals
    * Search
    * Academics
    * FOIA
* How to get data
    * Copy & paste
    * Curl
    * APIs
    * Scrapers
    * PDF / OCR
* Documenting provenance

### Chapter 10: Data cleanup

* What is bad data? 
    * Broken formats
        * Bad CSV formatting
        * Unclosed XML tags
    * Inconsistent data (usually human error)
        * Inconsistent spelling (of enumerations)
        * Inconsistent naming
        * Normalizing types
    * Wrong data 
        * Error/outlier/impossibility detection
        * Spreadsheet formatting issues
    * Bad constraints
        * Deduplication
        * Faux unique ids
        * Data not in discrete fields (first and last name, addresses, dates)
* Ways of cleaning it up
    * By hand
    * Spreadsheet formulas
    * Programming (Python)
    * Open Refine

### Chapter 11: Data processing 

How we use data processing to answer questions about our data.

* Tasks
    * Converting file formats
    * Joining tables
    * Adding/removing columns
    * Calculating aggregates/statistics
    * Querying/slicing 
* Scripts
    * Bash
    * csvkit
    * Python
    * SQL
	* R
* Documenting order of operations
* Documenting your code
* Naming things, revisited

### Chapter 12: Meta-processing

* Testing
    * Test assertions about the data
    * Test novel derived facts
* Shims, adapters and glue code
* Crons

