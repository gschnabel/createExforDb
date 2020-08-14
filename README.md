This script takes a directory with EXFOR masterfiles and stores
augmented EXFOR subentries in a MongoDB database.
The directory has to be specified in the script by replacing the
string `<PATH TO DIRECTORY WITH EXFOR ENTRIES>` with the actual
directory.

In more detail, the script accomplishes the following:

1. Read in the EXFOR masterfiles
2. Convert energy units to MeV and cross sections to millibarn
3. Merge the first subentry of each entry into the following subentries
4. Convert the augmented subentry to a JSON object
5. Add these JSON objects to a MongoDB database 

This script relies on the functionality of the packages *mongolite*, 
*data.table* and *exforParser*.
The unit conversion and merging of subentries is implemented in the
function [transformSubent] of the *exforParser* package.

[transformSubent]: https://github.com/gschnabel/exforParser/blob/5028766800464592ced6fc216712e08d0556b170/R/subent_transformation.R#L17
