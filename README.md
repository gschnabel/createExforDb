This script takes a directory with EXFOR masterfiles and stores
augmented EXFOR subentries in a MongoDB database.
In more detail, it accomplishes the following:

1. Read in the EXFOR masterfiles
2. Convert energy units to MeV and Cross sections to millibarn
3. Merge the first subentry of each entry into the following subentries
4. Convert the augmented subentry to a JSON object
5. Add these JSON objects to a MongoDB database 

This script relies on the functionality of the packages *mongolite*, 
*data.table* and *exforParser*.
The unit conversion and merging of subentries is implemented in the
function *transformSubent* of the *exforParser* package.
