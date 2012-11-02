
This project containts the styles for the nielsen project. 

GeoServer bugs
--------------


* Update the GeoServer REST API style delete to include the purge option
  The purge option actually removes the sld file on disk

* When a style or layer is added to layer group but does not exist, or
  GeoServer is unable to find it, the layer group is created anyway.
  This causes a number of issues. First if there are not layers, this
  new layer group does not show up in the GeoServer UI. It also fails
  to show up in the rest API.
  
* 
