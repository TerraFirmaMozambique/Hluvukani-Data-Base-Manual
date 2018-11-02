# Update Parcels & Related Tables

OPEN Excel File **Hluvukani\_C\_V1\_Parcelas.xlsx** FROM **Y:\projects\illovo\dbupdate**

Enable Content and Refresh All, via the data tab

On the macro tab, run the macro **form\_c\_prep\_csvs** from "This Workbook"

The following messages will appear:

![](.gitbook/assets/parcelas_update_warn.png)

![](.gitbook/assets/titulares_update_warn.png)

![](.gitbook/assets/novas_update_warn.png)

![](.gitbook/assets/testemunhas_update_warn.png)

![](.gitbook/assets/pontos_update_warn.png)

Answer YES to ALL

Close **Hluvukani\_C\_V1\_Parcelas.xlsx**

Open pgADMIN

Attach to the database tree of hluvukani

Open query tools, open file **hluvukani\_update\_form\_c\_all**

Execute the query

This updates TABLES:

* TABLE public.form\_c\_novas\_pessoas;
* TABLE public.form\_c\_parcelas
* TABLE public.form\_c\_pessoas\_rejeitado
* TABLE public.form\_c\_pontos
* TABLE public.form\_c\_tetsemunhas
* TABLE public.form\_c\_titulares
* TABLE public.update\_novas\_pessoas which is used in the Vfront for validating Proof of Life. [http://tfmoz.ddns.net/hluvukani/vfront/](http://tfmoz.ddns.net/hluvukani/vfront/) 

