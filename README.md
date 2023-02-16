# proc_export_zos

Background:
  SAS on z/OS does not like / have built into it, the proc export function.
  I would normally wrapper that in a macro on other platforms, and make it write CSV files etc.. for quick file sampling offloads.
  So you can't do that so easliy on mainframe, and the interactive sas tool is limited in cols and width,

This public work will enable you to make a variable file file of concatenated DLM data.
  The aim is to make a macro function with features to :
  * export up to 2x headers
    * field name
    *SAS format
  * rows up to N observaions - default 999999 - so you could whittle the sample beforehand or use this
  * provie an optional where (&expression) clause

Outputs:
  The output on z/OS will need to be into an allocated file.
  * So clearly, your file max lrecl will need to be able to hold this data - which is going to flex in size depending on column count and width of data
  * Therefore results for *all* datasets may vary or fail at times - depending on the dataset - too many columns, or data too wide - could exceed max lrecl.

Disclaimer:
  So this is intended for non-critical work.
  
See also:
  As an interim solution, the z/OS platform does have SAS macro %DS2CSV() built in.
  This is pretty good, and for now I am using it with a view to seeing how to improve upon it.
  
  See the sample_jcl.txt for something to use at present.
