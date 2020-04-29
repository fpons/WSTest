# Title #

Initial description

## Disclaimer ##
The following is intended to outline our general product direction. It is intended for information purposes only, and may not be incorporated into any contract. It is not a commitment to deliver any material, code, or functionality, and should not be relied upon in making purchasing decisions. The development, release, and timing of any features or functionality described for Oracle’s products remains at the sole discretion of Oracle.

## Requirements ##

List of requirements

## Step 1 ##

Let’s collect audit data created inside the database (view UNIFIED\_AUDIT\_TRAIL) and in operating system files (as per parameter audit\_file\_dest = /u01/oracle/admin/CONT/adump).

Go to **Secured Targets** > **Audit Trails** > **Add** and create the following three audit trails.

*Audit data stored in the Container database:*

*	audit trail type: **TABLE**
*	collection host: **secdb.localdomain**
*	secured target: **cont**
*	trail location: **UNIFIED\_AUDIT\_TRAIL**
*	collection plugin: **com.oracle.av.plugin.oracle**

*Audit data stored in the Pluggable database:*

*	audit trail type: **TABLE**
*	collection host: **secdb.localdomain**
*	secured target: **pdb1**
*	trail location: **UNIFIED\_AUDIT\_TRAIL**
*	collection plugin: **com.oracle.av.plugin.oracle**

*Audit data stored outside the database:*

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

We will start by loading DBSAT Discoverer’s report into Audit Vault.

From the desktop connection to secdb:

*	Login to Audit Vault as **AVADMIN/Reganam_1**
*	Go to **Secure Targets**
*	Click on **pdb1** to show the **Modify Secure Target** page
*	Scroll  down to **Sensitive Objects**

![Alt text](./images/img37.png " ")

* Browse to /home/oracle/HOL/lab01\_dbsat/dbsat/install/pdb1sensitivedata_discover.csv
*	Upload the csv file
*	click on **Save**

We can now add **PDB1** to the **Data Privacy compliance** report 


## Acknowledgements ##

- **Author** - Robert Pastijn, Database Product Management, PTS EMEA - April 2020
