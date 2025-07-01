# HA-roaf-tommekalender
Automasjon som henter ROAF tømmekalender datoer og lagrer det i home assistant kalender

## Blueprint

En ny Home Assistant blueprint `roaf_tommekalender` finnes under `blueprints/automation/roaf_tommekalender.yaml`.
Blueprinten henter tømmekalender for en gitt adresse fra ROAF sitt API og legger de neste datoene inn i valgt kalender uten å opprette duplikater.
Inputfeltene i UI krever app key, kommunenummer, gatenavn, gatekode, husnummer og kalenderen som skal brukes.

### rest_command `roaf_hent`

Blueprinten kaller et Home Assistant `rest_command` ved navn `roaf_hent` for å hente data fra ROAF API.
Legg følgende i `configuration.yaml` (eller i en inkludert fil):

```yaml
rest_command:
  roaf_hent:
    url: "{{ url }}"
    method: GET
    headers:
      Renovasjonappkey: "{{ headers.Renovasjonappkey }}"
      Kommunenr: "{{ headers.Kommunenr }}"
```

Automasjonen fyller inn variablene som brukes av `rest_command` når den kalles.
En eksempelfil `rest_command.yaml` følger med i repoet dersom du ønsker å
inkludere den direkte.

