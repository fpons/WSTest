# Title #

Initial description

## Disclaimer ##
The following is intended to outline our general product direction. It is intended for information purposes only, and may not be incorporated into any contract. It is not a commitment to deliver any material, code, or functionality, and should not be relied upon in making purchasing decisions. The development, release, and timing of any features or functionality described for Oracle’s products remains at the sole discretion of Oracle.

## Requirements ##

List of requirements

## Step 1 ##

Method 1

````
<copy>
cd /home/oracle/HOL/lab09_masking
mask20_clone.sh
</copy>
````

Method 2

````
$ <copy>cd /home/oracle/HOL/lab09_masking</copy>
````

````
$ <copy>mask20_clone.sh</copy>

SQL*Plus: Release 19.0.0.0.0 - Production on Tue Sep 3 13:24:23 2019
Version 19.3.0.0.0
Connected.
SQL> -- clone PDB1 as MASKED
SQL> create pluggable database masked from pdb1 keystore identified by "MyWalPwd#1";
Pluggable database created.

SQL> alter pluggable database masked open read write;
Pluggable database altered.

````

You can then connect to emcc as oracle and check whether the whole stack has been started by executing:

/u01/oracle/fmw/bin/emctl status oms

Wait until the whole stack is up

![Alt text](./images/img06.png " ")

## Step 3 : Cloning PDB1 ##

We start this exercise by creating a new pluggable database named **MASKED** as a clone of the production pluggable database PDB1. We will later run an **in-database anonymization** of PDB MASKED.

Using a terminal window to secdb, execute mask20_clone.sh to clone PDB1

````
$ <copy>cd /home/oracle/HOL/lab09_masking</copy>
````

````
$ <copy>mask20_clone.sh</copy>

SQL*Plus: Release 19.0.0.0.0 - Production on Fri Apr 24 14:45:38 2020
Version 19.6.0.0.0
Connected.

SQL> -- clone PDB1 as MASKED
SQL> create pluggable database masked from pdb1 keystore identified by "MyWalletPwd#1";
Pluggable database created.

SQL> alter pluggable database masked open read write;
Pluggable database altered.
````

To mask data and also because we operate in a Database Vault environment, we need to grant additional privileges to SYSTEM on MASKED.


### Substep 1.1 ###

Description of substep 1.1

### Substep 1.2 ###

Description of substep 1.2

## Step 2 ##

etc

## Acknowledgements ##

- **Author** - Robert Pastijn, Database Product Management, PTS EMEA - April 2020
