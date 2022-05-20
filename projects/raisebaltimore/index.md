Map 9 of Raise Baltimore Project for Mead & Hunt

Code used to export all 40 maps in arcpy:

import arcpy

aprx = arcpy.mp.ArcGISProject("CURRENT")
figFolder = arcpy.GetParameterAsText(0)

for lyt in aprx.listLayouts():
    print(" {0} ({1} x {2} {3})".format(lyt.name, lyt.pageHeight, lyt.pageWidth, lyt.pageUnits))
    lyt.exportToPDF(figFolder + "//" + lyt.name + ".pdf")  
