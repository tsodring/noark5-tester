Hvordan vedlikehodes nye kodeliste-oppføringer og annen metadata?
=================================================================

 ------------------  ---------------------------------
           Prosjekt  Noark 5 Tjenestegresesnitt
           Kategori  Versjon 1.0 beta
        Alvorlighet  protest
       Meldingstype  utelatt
    Brukerreferanse  pere@hungry.com
        Dokumentdel  7.2.2
         Sidenummer  165
        Linjenummer  n/a
    Innsendingsdato  ikke sendt inn
 ------------------  ---------------------------------

Denne teksten er del av en samling innspill til Noark5-standarden
tilgjengelig fra [https://github.com/petterreinholdtsen/noark5-tester/](https://github.com/petterreinholdtsen/noark5-tester/).

Beskrivelse
-----------

Dette gjelder del 7.2.2 (Kodelister) på side 165 og etterfølgende
sider.

Det fremgår ikke fra spesifikasjonen hvordan kodelister og andre
metadatalister får nye oppføringer.  Det er ikke oppgitt noen ny-*
type relasjoner for disse, og det er ikke nevnt noe om hvor de kan
finnes.  Uten slike operasjoner vil det ikke være mulig å vedlikeholde
kodelistene via API-et.

Det mangler både informasjon omdan hvor POST for nye oppføringer skal
fungere (dvs. hvordan ny-* URL der slike POST skal gjøres skal finnes)
og hva som er den unike URL for hver enkelt metadataoppføring der PUT
og DELETE skal utføres.

En ide for oppretting er å gjøre tilsvarende som for
http://localhost:8092/noark5v4/hateoas-api/arkivstruktur , der det
finnes en .../ny-arkivskaper/- og .../ny-arkiv/-relasjon for å lage
nye oppføringer i disse listene.  Dvs. å definiere en ny relasjon
http://rel.kxml.no/noark5/v4/api/metadata/ der alle ny-*-relasjonene
for oppretting av nye metadataoppføringer listes opp.  Slike
ny-*-relasjoner vil kun være synlige for priviligerte brukere som har
rett til å opprette nye listemedlemmer.  I tillegg til POST vil i
hvert fall operasjonene GET og OPTIONS fungere på disse
ny-*-oppføringene, tilsvarende for andre ny-*-operasjoner.

En tilsvarende ide for oppdatering og sletting er å gi hver
metadata-oppføring en SystemID og 'self'-relasjon med href til
http://rel.kxml.no/noark5/v4/api/metadata/dokumentmedium/&lt;systemID&gt;/
som så kan brukes til PUT og DELETE-opperasjoner ved oppdatering og
sletting.  Den bør naturligvis også fungere for GET for å kunne vite
hva som kan endres, selv om den normale måten å få ut kodelister og
andre metadata vil være å hente ut listen via den kjente relasjon en
til listen http://rel.kxml.no/noark5/v4/api/metadata/dokumentmedium/.

Ønsket endring
--------------

FIXME foreslå ny .../metadata relasjon og at det legges inn relasjoner
der for hver ny-* operasjon

FIXME foreslå at alle metadataoppføringer får 'self'-link,
f.eks. metadata/arkivstatus/systemid
