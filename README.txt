SequenceSubElementsWithinLocation.xsl

Sequences the subelements of <location>.  This should not make any other changes to the MODS record.  It is to clean up records where the subelements of <location> are in the wrong order, due to a bug in the Islandora forms that was in place from Islandora's launch (and is still in place pending a change to the transformation that runs on the MODS record at save).
To use this:
- Use the Islandora datastreams_io module to get the MODS records.
- Use Saxon to run the transformation on your desktop:
-- java -cp SaxonHE9-9-1-1J/saxon9he.jar net.sf.saxon.Transform -t directoryOfDownloadedMODSrecords/nameOfMODSrecord.xml -xsl:SequenceSubElementsWithinLocation.xsl -o:targetDirectoryForCorrectedRecords/nameOfMODSrecord.xml
-- (bash together the command for all MODS records you are working with)
- Use the Islandora datastreams_io module to replace the MODS records.