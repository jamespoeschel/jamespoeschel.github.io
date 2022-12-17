Raise Baltimore Project for the Maryland Transportation Administration through Mead & Hunt.

Crash data was sourced from the Maryland Open Data portal.

As the study corridor was long and the client needed a close up of crash hotspots and locations of pedestrian crashes, it was necessary to make 40 maps zoomed in along the corridor to show the data clearly.  The arcpy code used to efficiently export 40 maps is below:


import arcpy

aprx = arcpy.mp.ArcGISProject("CURRENT")
figFolder = arcpy.GetParameterAsText(0)

for lyt in aprx.listLayouts():
    print(" {0} ({1} x {2} {3})".format(lyt.name, lyt.pageHeight, lyt.pageWidth, lyt.pageUnits))
    lyt.exportToPDF(figFolder + "//" + lyt.name + ".pdf")  
