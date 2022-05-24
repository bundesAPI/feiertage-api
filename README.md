[[DE]](README.md)/[[EN]](README_en.md)

# Feiertage API

Der [Feiertage Webservice](https://feiertage-api.de/) bietet den Zugriff auf deutsche Feiertage im JSON-Format.

Das Tool basiert auf den Angaben von http://de.wikipedia.org/wiki/Feiertage_in_Deutschland. Auf der Wikipedia-Seite ist ersichtlich, dass manche Feiertage nicht im ganzen Bundesgebiet, sondern auf Bundeslandebene gelten. Die dort genannten Informationen sind im Tool hinterlegt.

Ebenso kann es spezielle Anmerkungen zu bestimmten Feiertagen geben (siehe Wikipedia-Seite). Auch diese Hinweise sind im Tool enthalten.

*Hinweis:* Für die Nutzung des Webservices mittels PHP haben die Ersteller eine Beispiel-Connector-Classe bereitgestellt, die jeder benutzen kann. Sie findet sich [hier](https://feiertage-api.de/api/Connector.php.txt).


## Anfragen

Die Nutzung des Webservices erfolgt durch einen GET-request an folgende URL:

**URL:** https://feiertage-api.de/api/

Alle Parameter sind einfache GET-Parameter, die der URL angehängt werden.


### Filter


**Parameter:** *jahr* 

Pflichtparameter, der ein beliebiges Jahr in Zahlenform annehmen kann, z.B. 2014.


**Parameter:** *nur_land* 

Wenn gesetzt, dann werden nur Feiertage des gewählten Bundeslandes angezeigt.
Mögliche Werte: 

- NATIONAL
- BW
- BY
- BE
- BB
- HB
- HH
- HE
- MV
- NI
- NW
- RP
- SL
- SN
- ST
- SH
- TH

NATIONAL=Bundesweit anerkannte Feiertage, BW=Baden-Württemberg, BY=Bayern, BE=Berlin, BB=Brandenburg, HB=Bremen, HH=Hamburg, HE=Hessen, MV=Mecklenburg-Vorpommern, NI=Niedersachsen, NW=Nordrhei-Westfalen, RP=Rheinland-Pfalz, SL=Saarland, SN=Sachsen, ST=Sachsen-Anhalt, SH=Schleswig-Holstein, TH=Thüringen. 


**Parameter:** *nur_daten* 

Wenn gesetzt (Wert egal, z.B. auf 1), dann werden keine bundeslandspezifischen informationen ausgegeben, sondern alle deutschen Feiertage samt Datum ausgegeben.


**Parameter:** *callback* 

Wenn gesetzt, dann wird die Ausgabe in eine JSONP-Funktion eingebettet.


### Beispiel

```bash
feiertage=$(curl -m 60 'https://feiertage-api.de/api/?jahr=2022&nur_land=BY')
```
