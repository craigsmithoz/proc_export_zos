# proc_export_zos

SAS on mf does not like/have built in, the csv export function.
This will enable you to make a variable file file of concatenated DLM data

Clearly, your file max lrecl will need to be able to hold this data - which is going to flex in size depending on column count and width of data
So results may be limited or not work as desired - depending on dataset

this is intended for non-critical work, clearly.


haha.. discovered %DS2CSV().. brilliant. saved me work
