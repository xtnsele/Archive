**Retrieve Oracle version information**

This will show you how to retrieve Oracle Version number (information)

**Syntax**

Run

    SELECT * FROM v$version;

This give all relevant information from Oracle

or 

    SELECT * FROM v$version
    WHERE banner LIKE 'Oracle%';

This gives the version only

[https://www.techonthenet.com/oracle/questions/version.php](https://www.techonthenet.com/oracle/questions/version.php)