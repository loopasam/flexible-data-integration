Supplementary data for the manuscript "Flexible Data Integration and Curation using a Graph-Based Approach".

# Files and content

- `drugs.csv`: Database serialized as flat file of tab-separated values. Column 1 contains a unique technical identifier for an entry, column 2 the value of a synonym and column 3 the type of the synonym.
- `Excluded_nodes_stepX.txt`: Extract of the excluded records by the methodology for cleaning step X. The file lists the record excluded and the graph to which they belong to for comparison.

# Examples

This section illustrates a couple of examples where records where excluded from a graph by the methodology.

## Erroneous salt information

Graph contains:
- `CHEMBL20` (https://www.ebi.ac.uk/chembl/compound/inspect/CHEMBL20)
- `CHEMBL1200814` (https://www.ebi.ac.uk/chembl/compound/inspect/CHEMBL1200814)
- `CHEBI:27690` (http://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:27690)
- `CHEBI:31163` (http://www.ebi.ac.uk/chebi/searchId.do?chebiId=31163)
- `CHEBI:50634` (http://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI:50634)
- `DB00819` (http://www.drugbank.ca/drugs/DB00819)
- `DBSALT000539` (salt - http://www.drugbank.ca/drugs/DB00819)

Record to be excluded is `CHEMBL20`, as it erronously contains a synonym referring to the version of the molecule with a sodium ion ("Acetazolamide Sodium").
The other sources make a clear distinction between the molecule with (`CHEBI:31163`, `DBSALT000539`) and without sodium ion (`CHEBI:27690`, `DB00819`),
therefore the record must be excluded from the database to improve consistency.

## Mixtures

Graph contains:
- `DB02187_1` (mixture - http://www.drugbank.ca/drugs/DB02187)
- `DB00286` (http://www.drugbank.ca/drugs/DB00286)
- `CHEBI:8389` (http://www.ebi.ac.uk/chebi/searchId.do?chebiId=CHEBI%3A8389)
- `CHEMBL1201649` (https://www.ebi.ac.uk/chembl/compound/inspect/CHEMBL1201649)
- `CHEMBL1201466` (https://www.ebi.ac.uk/chembl/compound/inspect/CHEMBL1201466)
- `CHEMBL2106240` (https://www.ebi.ac.uk/chembl/compound/inspect/CHEMBL2106240)

Record to be excluded is `DB00286`, as it broadly refers to "Conjugated Estrogens", containing many different drug products and linking to the other more specific entries.