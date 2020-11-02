---
layout: page
title: "Rekommendation"
category: doc
date: 2020-10-21-rekommendation.md
order: 1
---
För att inte skapa merarbete för individuella livsmedelsinspektörer är det önskvärt att kommunernas systemleverantörer bygger in stöd för att följa specifikationen i sina system. Ett API och integration med lokal dataportal rekommenderas för att exponera ny och uppdaterad data per automatik och i nära realtid. Data som tillgängliggörs via API:et bör vara i JSON-format, och följa strukturen nedan. Se även bifogad teknisk specifikation för mer detaljer.

<img src="/livsmedel/assets/images/rekommendationer_bild1.png" width="50%"/>

Som andrahandsalternativ kan en statisk JSON-fil tillgängliggöras med jämna mellanrum, vilken följer samma struktur. Denna fil bör då _ersätta_ tidigare publicerad fil, samt innehålla all data enligt urval listat nedan.

Beroende på tekniskt stöd, kan också en CSV-fil tillgängliggöras men det är ej att föredra p.g.a. den något lägre nivån på struktur och enkelhet i att bearbeta datamängden för användaren. CSV-filen ska följa samma struktur som JSON-filen, och ej replikera information mellan rader – dvs de kolumner som inte är aktuella för dataposten lämnas tomma snarare än att kopplas till varandra.

Önskvärd frekvens för uppdatering är dagligen, och minst en månatlig uppdatering bör göras för att följa rekommendationen.

Filen, filerna eller utdata från API:et ska vara:

- UTF-8 kodad
- Publicerad på internet utan krav på registrering eller begränsningar
- CSV-filer ska använda kommatecken (,) som avdelare, citationstecken som textavgränsare (&quot;), och CRLF som radbrytning
- Beskrivna med metadata enligt [Beskriva öppna livsmedelskontroller](/livsmedel/misc/DCAT-AP-SE.html)

Rekommendationer för urval av data:

1. Information om den inspekterande myndigheten måste finnas med.
2. Alla inspektioner för en anläggning ska finnas med - minimikravet är de senaste inspektionerna som täcker in samtliga relevanta inspektionspunkter på ett rullande schema. Detta uppskattas omfatta ca 3 års löpande inspektioner vid varje tidpunkt. Det är dock önskvärt med en längre tidshorisont om möjligt.
3. Information om de anläggningar vars inspektioner listas ska finnas med.
4. Undvik att ta med information om anläggningar som varit _&quot;vilande&quot;_ eller _&quot;upphörda&quot;_ under hela tidsperioden. Detta innebär dock att anläggningar som inte idag är aktiva, men har varit det någon gång under de senaste 3 åren, ska inkluderas i urvalet.

Det är viktigt att informationen blir synlig på Sveriges dataportal dataportal.se. För att åstadkomma detta bör kommuner bör följa DCAT-AP-SE standarden vid beskrivning av metadata och registrera denna i dataportalen. Se [Beskriva öppna livsmedelskontroller](/livsmedel/misc/DCAT-AP-SE.html). Det är också lämpligt att visa öppna data på kommunens egen webbplats och eventuella regionala portaler.

## Visualisering av förhållande mellan datamängd, resurser samt metadata

Nedan redogörs för förhållandet mellan datamängder, resurser, samt metadata.

<img src="/livsmedel/assets/images/rekommendationer_bild2.png" width="50%"/>

## Diskussion om rekommendationen

Om det finns frågor, funderingar eller andra tankar kring rekommendationen så kontakta [filip.dijak@knowit.se](mailto:filip.dijak@knowit.se), [sjogren.joel@adlittle.com](mailto:sjogren.joel@adlittle.com) eller [bjorn@hagstrom.nu](mailto:bjorn@hagstrom.nu).

## Licenser

Allt material som publiceras enligt denna specifikation ska vara tillgänglig med en Creative Commons Zero (CC-0) licens, vilket i korthet innebär att vem som helst kan använda den öppna datamängden till vad som helst.
