# Working Notes on OCC Hluvukani

The table\_OCC\_Master data is collated into one sheet “OCC\_MASTER” through the excel worksheet occ\_workthrough. This data has already been submitted from the field and updated in Form B and Form C and is the data which needs verification through the OCC phase of the program.

The table\_OCC\_master is used by oobase database to produce the OCC village lists.



The data in the table OCC MASTER is not the data we need to edit… and is therefore not editable.

OCC – workthrough.

•	Refresh all

•	Clear all the data, but not headers from the sheet OCC-MASTER

•	Copy the data from occ\_1 \( the data from Form B\)

•	Paste the copied data into Sheet OCC-MASTER in A2 use past data and formatting 

o	Filter data in party number = 1 and delete these entries with the null values.

o	Ctrl+down arrow to end of data block

•	Copy all the data from occ\_2 \( the data added from nova\_pessoas in form C\)

•	Paste the data at the end of the datablock in OCC-MASTER sheet

o	Sort all of the data by region, bloco, parcel\_id and party\_id

•	Populate the key column \(L\) as:

o	uuid, nome, doc, doc\_no  

o	=CONCATENATE\(A2," ",F2," ",J2," ",K2\)

•	Copy all of the data and headers 

•	Open a blank workbook

•	Paste special into a new sheet values and number formatting

•	Run Find and replace find 00/01/1900 in the “nas” column and replace with nothing \(leave replace null\)

•	Select the whole sheet and remove duplicates based on key value only

•	Save the new sheet as Hluvukani\_table\_occ\_master CSV \(comma delimited\) replace existing sheet

•	Open pgAdmin connect to the Hluvukani database 

•	Run the updating query for table\_OCC\_Master path is:

o	\\tfmoz.ddns.net\share\projects\illovo\ODK Forms\hluvukani-odk-forms\Hluvukani\_SQL\ update\_OCC\_master.sql

o	This replaces the table in the database. 

You can now produce new lists for the OCC through OObase based on the information held in the database. 

--------------------------------------------------------------------------------------------------------------------------------------

The data in database table form\_d\_occ

This the data returned from the field through Hluvukani D Objeccoes e Correcoes Hluvukani\_D\_V2 & Hluvukani\_D\_V3 and is collated through the excel worksheet Hluvukani\_D\_OCC. This data indicates the changes that need to be made to the data in the two database tables form\_b\_pessoas  & form\_c\_novas\_pessoas via the OCC procedure.

Normally the data in form\_d\_occ would not be editable, unfortunately due to poor data submissions and lack of controls, erroneous data has been entered from the field. Therefore form\_d\_occ is now editable through VFRONT to rectify the problems.

What are the problems., 

1.	The party number \(1\) is the biggest problem and in cases where multiple people are associated with a parcel it requires subjectivity to define which person requires a change and reassignment of the party number and the subjectivity cannot at this stage be handled by an SQL query. 

2.	In trying to normalise the multiple entries of people added through form C and adding a single entry to form B and therefore attributing a definitive party number \(Party\#\#\#\). Some entries have been missed off the production of previously produced OCC lists sent to the field. This omission was mainly due to the data entry of new persons in form C being entered differently by the same and different people and with different field attributes which do not allowing the standardised normalisation of the added people through SQL code. i.e. use or none use of cedillas, acute accents, circumflex accents, grave accents or tildes in names; the phonetic spellings of names; transposition of numbers or miss entry of dates.

How to rectify the problems.

There are no issues with those parcels that are marked as ”certify” as they can be processed immediately for certification.

However, we do have problems with those listed as “change” the main problem is the identification of the person through SQL that the changes need to be applied to. As many are numbered “1” submitted by the field CF’s. This can only be done with manually with the aid of the list that was sent out with the appropriate OCC maps for the region and block.

---------------------------------------------------------------------------------------------------

Updating the database table form\_d\_occ 

Open the excel spreadsheet Hluvukani\_D\_occ.

Run the macro update\_prep this saves a CSV output as: \\tfmoz.ddns.net\share\projects\illovo\dbupdate.Hluvukani\_D\_occ.csv 

Open pgAdmin and run: 

\\tfmoz.ddns.net\share\projects\illovo\ODK Forms\hluvukani-odk-forms\Hluvukani\_SQL\update\_form\_d\_occ.sql  this updates the database table with the returns from the ODK in the field.

-----------------------------------------------------------------------------------------------------------

Altering the Records

The OCC returns are now sorted in the Vfront form OCC\_Form\_D for editing of errors, the sorting order is based on region, bloco, upn, party.

The number in the Party Field has two forms where \# = a number from 0 – 9

Party\#\#\#\# or

\#\#\#\# 

Each of the Numbers must be as they are shown on the OCC Village lists.



We currently have 161 entries from 812 that need immediate clarification and resolving. Up until all the numbers are sorted in the table\_form\_d\_occ we will have duplicates in the table which still may cause issues with updating form b or Form C.









