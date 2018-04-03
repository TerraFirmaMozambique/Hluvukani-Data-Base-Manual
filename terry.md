Updating the declaration table \(public.certification\) Illovo hluvukani database.

After OCC has been completed and names and detailes altered through VFront and spatial data has been corrected in QGIS

open the pgAdmin and run the SQL file Certification\_process\_\_\_complete.sql

This drops the normalisation table "public.normalise\_form\_d\_occ" and allows for all changes to be reloaded, this is incase there has been any changes to the previously refused certificates due to settlement of dispute or of all parties associated with a parcel now having their state altered to certify.

It rebuilds the table based on a nested select query from form\_d_\__occ which are the returns from the ODK form D that have been adjusted through VFront... 

Nested sql manages changes to the parcel number which may have been made to reflect in the persons added through form C.

The "public.party" table is dropped and rebuilt, which reflects any changes made to the Persons in form B or those new persons added in form C.

An declarations updating table is constructed and any new declerations are added to the public.certification table with the associated production date 'now' the geom is transformed from WGS84 to WGS84/UTM36S and areas and MIN MAX X & Y 's are calculated and the table updated



---------------------------------------

Thoughts for ongoing administration: 

1. Need to produce list of Parcels not certified and the reason why so they can be further investigated
2. Need to produce a list giving a count of certificates and the date they where produced on
3. 










 





