# Information Management for Journalists

## Introducing data

### Chapter 1: Introduction & simple (primitive) data types

* Teacher introduction 
* What is information management?
    * Methods for organizing and structuring information for analysis and retrieval.
* Prerequisites for this course
    * Basic understanding of spreadsheets
    * Ability to use Google
* By the end of this course, you will...
    * Understand data at a fundamental level.
    * Know how to process data in a systematic and rigorous manner.
    * Have a broad understanding of the available tools for working with data.
    * Bee able to make an informed decision about what tool is most appropriate for given a course
* As this is a survey course, you will not...
    * Become an expert programmer.
    * Develop a deep understanding of algorithms.
    * Learn the inner workings of any complex software.
    * Master any single tool.

An overview of various types of data, with a cursory look into how each is stored/represented by the computer. Each type will be illustrate with examples from a variety of applications (Excel, Python, etc). The difference between syntax and semantics.

* Numbers (bytes, ints, uints, floats)
* Text (chars, strings)
* Boolean
* Enumerations
* Binary blobs (images, audio)

### Chapter 2: The command line and complex data types

A quick introduction into the command line, which will be used to explore data from here on out.

* Firing it up
* Navigation: cd, ls
    * Arguments and flags
    * --help
* Running programs: man, python
* Searching: cat, grep
    * Pipes
* Scripts
* exit

Delving deeper into types by analyzing how they can be combined together to form complex data types. We will discuss the various these types may be serialized (JSON, XML, etc). Revisit syntax versus semantics. 

* Lists (1D)
* Tables (2D)
* Relationships (3 or more dimensions)
* Maps / hashes / key-value pairs...
* ...objects (nested data)

### Chapter 3: metadata

Types of data that document how your data works. Illustrate types with both examples and counterexamples.

* Functional
    * Explicit (database schemas) v. implicit (column definitions)
    * Unique ids
    * Foreign keys
    * Constraints ("business rules")
    * Text encodings (ascii, unicode, latin-1)
* Non-Functional
    * Author
    * Creation date
    * Modification date


## Storing data

### Chapter 4: storing simple datasets

Survey the available methods for storing simple lists and tables. Discuss what primitive types are supported by different formats.

* Lists: Plain text
* Tables: Spreadsheets
    * CSVs
    * Excel
    * Google Spreadsheets

### Chapter 5: storing complex datasets 

Discuss ways of storing multi-table or nested data. Briefly explore the universe of databases and how they are relevant to different applications.

* Relationships: SQL Databases (MySQL, PostgreSQL, sqlite)
* Flat (serialized) objects: JSON, XML, YAML
* Object Databases MongoDB, CouchDB
* Search-oriented: PANDA
* Big data: Hadoop


## Tracking changes

### Chapter 6: Understanding versions

Understanding versions as different files that are logically connected to one another by some process. What processes cause changes?

* What constitutes a change in version?
    * Changed data
        * Revision
        * Modification
        * Cleanup
        * Conversion
        * Derived values
        * Processing
    * Added data
    * Removed data
* Sometimes it makes sense to record that things don't change too
    * We know something hadn't changed by a certain time
* Ways of identifying difference
    * File size
    * Hash (md5)
    * Byte-wise comparison (diff)
* Three places to track changes:
    * The dataset
    * The row or object
    * The individual value

The most common way of tracking changes is at the dataset level using naming patterns.

* The timestamp: atomic unit of change
* Files and folders (a.k.a naming things)
    * Always name from less specific to more specific
    * Always timestamp things you're changing
    * Always make copies (you have unlimited hard drive space--use it)

### Chapter 7: Advanced versioning

Tracking dataset level changes with naming patterns can quickly become cumbersome. Here we'll describe tech for automating the process, look at some examples of using it and discuss cases where it fails.

* Dropbox: The poor man's version control
* git: The engineer's version control
    * git in 5 minutes
    * Commit messages matter
    * Works for text formats (CSV, flat files), but not for binaries
    * Not designed for big data

Tracking changes at the row and value-level is not as frequently necessary and much, much more complicated.

* Creation and modification dates
* Change tables and data warehouses: creating problems to solve problems
    * Versioning as metadata


## Data pipelines

### Chapter 8: Repeatable processes and acquiring data

The most important thing we can do to when handle data is create repeatable processes. We'll refer to these as data pipelines. These pipelines may produce many outputs and may be bespoke or generic.

* Answering questions with data
* Ensuring provenance of the data
* Depend against attacks on integrity
* Self-documenting workflow
* Show your work

The first part of any data pipeline is acquiring data.

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
* Documenting field definitions
    * Enumerations

### Chapter 9: Data cleanup

Data is never perfect. The second step in most data pipelines is cleaning and normalizing the data.

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

### Chapter 10: Data processing 

Once you have data and it's cleaned up, now it's time to use it to answer our questions. We do this by crafting scripts that process the data and output new pieces of data.

* Tasks
    * Converting file formats
        * Beware lossy conversions! (e.g. losing decimal precision)
    * Joining tables
    * Adding and removing columns
    * Calculating aggregates and statistics
    * Querying, grouping and slicing 
* Scripts
    * Bash (the command line revisited)
    * csvkit
    * Python
    * SQL
	* R
* Documenting order of operations
* Documenting your code
* Naming things revisited: scripts

### Chapter 11: A complete data pipeline

???

### Chapter 12: Meta-processing

* Testing
    * Test assertions about the data
    * Test novel derived facts
* Shims, adapters and glue code
* Crons

