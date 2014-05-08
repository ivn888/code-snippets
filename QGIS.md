QGIS
====

Actions
-------

| Name         | Type | Action |
| ------------ | ---- | ------ |
| RF simplifié | Open | ```http://www.rfinfo.vd.ch/rfinfo.php?no_commune=[%substr("IDENTDN", 4, 3)%]&no_immeuble=[%"numero"%]``` |
| RF complet   | Open | ```https://secure.vd.ch/territoire/intercapi/faces?bfs=[%substr("IDENTDN", 4, 3)%]&kr=0&n1=[%"numero"%]&type=grundstueck_grundbuch_auszug&sec=<key>&intercapi=Extrait+RF+online``` |

Settings
--------

```python
from PyQt4.QtCore import QSettings
s = QSettings()

# Display all settings
for k in s.allKeys(): print k, ":", s.value(k)

# Read a setting
s.value("Qgis/stylesheet/fontFamily")

# Write a setting
s.setValue("Qgis/stylesheet/fontFamily", u"Arial")
```

### Default settings

To run QGIS with default settings, add the command line option ```--optionspath``` at the end of the target in ```%ProgramFiles%\QGIS <version>\bin\qgis.bat```:

```batchfile
qgis-bin.exe --optionspath c:/temp/qgis
```

A new settings file will be created (```QGIS/QGIS2.ini```) and used instead of the stored ```QSettings```.

> With the command line option ```--configpath```, QGIS will use the given path for all user configuration (```QSettings``` and ```.qgis2``` folder).