[[DE]](README.md)/[[EN]](README_en.md)

# Holidays API

The [Holidays Web Service](https://feiertage api.de/) of [Julian Richter](https://www.paypal.com/donate?token=-JAL84u4LbrgiDzVqvJqWOnqhusn30r_FwEBT65n0kqlZd7FTRidVBPL9kjFsKIOsZaqFTEm0jz6_JVm) provides access to German holidays in JSON format. 

The tool is based on the information provided by http://de.wikipedia.org/wiki/Feiertage_in_Deutschland. On the Wikipedia page it can be seen that some holidays do not apply throughout Germany, but at the state level. The information mentioned there is integrated in the tool. 

There may also be special comments on certain holidays (see Wikipedia page). These comments are also included in the tool. 

*Note:* For the use of the web service using PHP, the creators have provided a sample connector class that anyone can use. It can be found [here](https://feiertage-api.de/api/Connector.php.txt).


## Requests

Applying the web service requires a GET-request to the following URL: 

**URL:** https://feiertage-api.de/api/

All parameters are simple GET parameters that are appended to the URL.


### Filter


**Parameter:** *jahr* 

Mandatory parameter that can take any year in numerical form, e.g. 2014


**Parameter:** *nur_land* 

If set, only holidays of the selected state are displayed. 
Possible values:

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

NATIONAL=Nationally recognized holidays, BW=Baden-Württemberg, BY=Bayern, BE=Berlin, BB=Brandenburg, HB=Bremen, HH=Hamburg, HE=Hessen, MV=Mecklenburg-Vorpommern, NI=Niedersachsen, NW=Nordrhei-Westfalen, RP=Rheinland-Pfalz, SL=Saarland, SN=Sachsen, ST=Sachsen-Anhalt, SH=Schleswig-Holstein, TH=Thüringen. 


**Parameter:** *nur_daten* 

If set (value does not matter, e.g. to 1), then no state-specific information is returned. Instead, all German holidays as well as their date are returned.


**Parameter:** *callback* 

If set, then the output is embedded in a JSONP function.


### Example

```bash
holidays=$(curl -m 60 'https://feiertage-api.de/api/?jahr=2022&nur_land=BY')
```

