# Title #

Initial description

## Disclaimer ##
The following is intended to outline our general product direction. It is intended for information purposes only, and may not be incorporated into any contract. It is not a commitment to deliver any material, code, or functionality, and should not be relied upon in making purchasing decisions. The development, release, and timing of any features or functionality described for Oracle’s products remains at the sole discretion of Oracle.

## Requirements ##

List of requirements

## Step 1 ##

Let’s collect audit data created inside the database (view UNIFIED\_AUDIT\_TRAIL) and in operating system files (as per parameter audit\_file\_dest = /u01/oracle/admin/CONT/adump).

Go to **Secured Targets** > **Audit Trails** > **Add** and create the following three audit trails.


*	audit trail type: **TABLE**
*	collection host: **secdb.localdomain**
*	secured target: **cont**
*	trail location: **UNIFIED\_AUDIT\_TRAIL**
*	collection plugin: **com.oracle.av.plugin.oracle**


*	audit trail type: **TABLE**
*	collection host: **secdb.localdomain**
*	secured target: **pdb1**
*	trail location: **UNIFIED\_AUDIT\_TRAIL**
*	collection plugin: **com.oracle.av.plugin.oracle**


*	audit trail type: **DIRECTORY**
*	collection host: **secdb.localdomain**
*	secured target: **cont**
*	trail location: **/u01/oracle/db/admin/CONT/adump**
*	collection plugin: **com.oracle.av.plugin.oracle**


The collection should start automatically after a few seconds.

````
$ <copy>Optional copy of values</copy>

Some more text
Some more
````



## Acknowledgements ##

- **Author** - Robert Pastijn, Database Product Management, PTS EMEA - April 2020
