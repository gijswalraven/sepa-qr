# SEPA QR-generator

Maak een betaal-QR die je bank-app kan scannen, en die niet verloopt zoals een betaalverzoek.

**Gebruik het direct:** https://gijswalraven.github.io/sepa-qr/

## Wat het doet

Je vult de naam van de ontvanger, het IBAN, een bedrag en een omschrijving in. De pagina maakt daarvan een QR-code in het EPC-formaat (ook wel *SEPA QR* of *Girocode*). Scan de code met je bank-app en de betaling staat klaar.

De QR-code bevat de gegevens zelf. Daarom is er geen server die een betaalverzoek bewaart, en daarom verloopt de code niet.

- Het bedrag is optioneel. Zonder bedrag kiest de betaler zelf.
- De afbeelding bevat onder de QR een leesbare strook met bedrag, naam, IBAN en omschrijving.
- Met **Bewaar afbeelding** sla je die afbeelding op als PNG, zodat je hem kunt delen of afdrukken.
- Met **Kopieer QR-tekst** kopieer je de ruwe EPC-tekst.

## Privacy

Alles wat je invult blijft in je eigen browser. Er wordt niets verstuurd of opgeslagen, er zijn geen cookies en er is geen analytics.

Wel komen twee dingen van internet: de lettertypen (Google Fonts) en de QR-bibliotheek [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) (via cdnjs). Die verzoeken bevatten geen van jouw gegevens.

## Zelf gebruiken of aanpassen

De hele tool is één bestand: [index.html](index.html), zonder build-stap.

- **Downloaden:** onderaan de pagina staat een link om hem als zip te downloaden.
- **Lokaal draaien:** open `index.html` in je browser.
- **Zelf hosten:** zet `index.html` op elke statische host. Voor GitHub Pages: fork deze repo en zet onder *Settings → Pages* de branch `main` aan.

## Velden en regels

| Veld | Regel |
| --- | --- |
| Naam ontvanger | verplicht, maximaal 70 tekens |
| IBAN | verplicht, wordt gecontroleerd met de IBAN-controlesom |
| Bedrag | optioneel, 0,01 tot 999.999.999,99 euro |
| Omschrijving | optioneel, maximaal 140 tekens |
| BIC | optioneel, bij SEPA niet meer nodig |

De QR gebruikt versie 002 van het EPC-formaat met UTF-8 en foutcorrectieniveau M.

## Let op

Controleer na het scannen altijd naam, IBAN en bedrag in je bank-app voordat je betaalt. Deze tool is niet gekoppeld aan een bank en geeft geen garantie dat een bank-app de code ondersteunt.

## Licentie

[MIT](LICENSE). Je mag de tool gebruiken, kopiëren, aanpassen en delen, ook zelf hosten, zolang de licentietekst erbij blijft.
