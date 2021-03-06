Klargjør om relasjoner skal ha avsluttende skråstrek
====================================================

 ------------------  ---------------------------------
           Prosjekt  NOARK 5 Tjenestegresesnitt
           Kategori  Versjon 1.0 beta
        Alvorlighet  kommentar
       Meldingstype  trenger klargjøring
    Brukerreferanse  pere@hungry.com
        Dokumentdel  6.1.1
         Sidenummer  11
        Linjenummer  14
    Innsendingsdato  2017-03-30
 ------------------  ---------------------------------

Beskrivelse
-----------

Gjelder også side 12-13 og 25-26.

I spesifikasjonen har alle navnene på HATEOAS-relasjoner avsluttende
skråstrek i tabeller over relasjoner.  Det samme gjelder de fleste
andre plasser der http://rel.kxml.no/ er omtalt.  Se f.eks. 6.1.1.3
(Opprette objekter (create)) side 16, 6.1.1.4 (Preutfylling av objekt)
side 18, 7.2.1.1 (Arkiv) side 57, 7.2.1.2 (Arkivdel) side 66 og videre
ut over i dokumentet.  Men det er noen få eksempler der disse navnene
er oppgitt uten avsluttende skråstrek, nemlig i teksten på side 12-13
og 25-26.  I tillegg oppgir demonstrasjons-API-et tilgjengelig fra
[n5test.kxml.no](http://n5test.kxml.no/api/) konsekvent alle
relasjonsnavnene uten avsluttende skråstrek.  I sum blir det dermed
uklart om navnene på disse relasjonsnøklene skal oppgis med eller uten
avsluttende skåstrek.

Skal det være http://rel.kxml.no/noark5/v4/api/arkivstruktur/fil/
eller http://rel.kxml.no/noark5/v4/api/arkivstruktur/fil eller er det
meningen at begge skal brukes om hverandre?

Det blir enklere å lage en API-klient hvis det er entydig hvordan
slike relasjonsnøkler skal navngis, da en alltid vet hva en skal se
etter i det som returneres fra tjeneren, og slipper å teste om en
finner nøkler med eller uten skråstrek.  Jeg foreslår derfor å fastslå
i teksten hva som er riktig, og endre spesifikasjonen slik at alle
forekomster av relasjonsnøkler oppgis på samme måte.

Jeg anbefaler å konkludere med at de fleste forekomster i
spesifikasjonen er korrekt og fikse de få avvikende delene, dvs. at
det alltid skal være avsluttende skråstrek i slike relasjonsnøkler.

Dette er i tråd med hvordan i hvert fall Apache håndterer
katalogoppslag, der oppslag på http://tjener/katalog mottar en
HTTP-omdirigering til http://tjener/katalog/ før innholdet returneres.
I slike tilfeller er det altså en fordel å oppgi URL med avsluttende
skråstrek, for å slippe unna med ett HTTP-oppslag i stedet for to.

Ønsket endring
--------------

Legg inn ny setning under andre setning i punkt 6.1.1 på side 11, dvs. at

> «Dette gjøres med ressurslenker og relasjonslenker som inneholder
> beskrivelse av ressursen med eksempler på forespørsler, resultat og
> statuskoder.»

endres til

> «Dette gjøres med ressurslenker og relasjonslenker som inneholder
> beskrivelse av ressursen med eksempler på forespørsler, resultat og
> statuskoder.  Alle slike ressurslenker og relasjonslenker har
> avsluttende skråstrek.»

I tillegg to to forekomstene i teksten som mangler skråstrek, dvs.
endre i del 6.1.1.1 og 6.1.1.2 på side 12 og 13:

* «http://rel.kxml.no/noark5/v4/api/arkivstruktur» og
* «http://rel.kxml.no/noark5/v4/api/sakarkiv»

til

* «http://rel.kxml.no/noark5/v4/api/arkivstruktur/» og
* «http://rel.kxml.no/noark5/v4/api/sakarkiv/»

samt endre i del 6.1.1.9 på side 25 og 26:

* «http://rel.kxml.no/noark5/v4/arkivstruktur/fil» og
* «http://rel.kxml.no/noark5/v4/arkivstruktur/dokumentobjekt»

til

* «http://rel.kxml.no/noark5/v4/arkivstruktur/fil/» og
* «http://rel.kxml.no/noark5/v4/arkivstruktur/dokumentobjekt/»

Respons
-------

Ingen respons fra arkivverket så langt.

Også registrert som
https://github.com/arkivverket/noark5-tjenestegrensesnitt-standard/issues/15
