# Updating Data on People

OPEN Excel File **Hluvukani\_B\_Registrar\_Pessoas.xlsx** FROM **Y:\projects\illovo\dbupdate**

Enable Content and Refresh All, via the data tab

On the macro tab, run the macro **hluvukani\_b** from "This Workbook"

The following message will appear:

![](/assets/people_update_warn.png)

Answer YES

Close Hluvukani\_B\_Registrar\_Pessoas.xlsx

Open pgADMIN

Attach to the database tree of hluvukani

Open query tools, open file **hluvukani\_update\_form\_b\_pessoas** 

Execute the query



This updates TABLE “public.update\_form\_b\_pessoas” in the database

It also places a new names lists for use in form C in “/var/lib/share/projects/illovo/ODK Forms/hluvukani-odk-forms/Hluvukani\_C\_registrar\_parcelas/Hluvukani\_C\_registrar\_parcelas-media/” AS:

* Norte.csv
* Central.csv
* Sul.csv



