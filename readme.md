
This project containts the styles for the nielsen project. 

GeoServer issues
----------------


* Update the GeoServer REST API style delete to include the purge option
  The purge option actually removes the sld file on disk

* When a style or layer is added to layer group but does not exist, or
  GeoServer is unable to find it, the layer group is created anyway.
  This causes a number of issues. First if there are not layers, this
  new layer group does not show up in the GeoServer UI. It also fails
  to show up in the rest API.
  
  A empty xml element is created in the configuration object.
  
* Via the GeoServer rest api one is not able to create a new LayerInfo
  object. 
  
* In the rest api via the json serialization xstream system, Java class
  names are leaked into the json representation.
  
* When a given a in correct json representation of a *Info object, the
  GeoServer rest api throws a hard to read xstream exception. 
  
  For example, when updating a LayerInfo object via the rest API with
  JSON, I forgot to "hang" all of the information off a layer key in
  the json object. As a result GeoServer looks to convert the object
  off the first key its finds. In this case is was the enabled
  key. Since GeoServer can't match the "enabled" key to a class it
  throws an exception here. However this is kind of a false error.
 
