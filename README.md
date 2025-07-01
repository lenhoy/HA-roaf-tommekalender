# HA-roaf-tommekalender
Automasjon som henter ROAF tømmekalender datoer og lagrer det i home assistant kalender

## Blueprint

En ny Home Assistant blueprint `roaf_tommekalender` finnes under `blueprints/automation/roaf_tommekalender.yaml`.
Blueprinten henter tømmekalender for en gitt adresse fra ROAF sitt API og legger de neste datoene inn i valgt kalender uten å opprette duplikater.
Inputfeltene i UI krever app key, kommunenummer, gatenavn, gatekode, husnummer og kalenderen som skal brukes.

