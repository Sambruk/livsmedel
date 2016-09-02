---
layout: page
title: "Inspektioner"
category: doc
date: 2016-09-02 14:02:59
order: 3
---
En *inspektion* är när en inspektör har inspekterat en anläggning, t.ex. genom ett besök eller via en s.k. *"skrivbordsinspektion"*. Endast den senaste inspektionen för en anläggning **måste** finnas med i inspektionsfilen, men det är rekommenderat att alla inspektioner för en anläggning finns med. Många *inspektion* objekt listas i ett *inspektioner* objekt.

|Attribut|Typ|Beskrivning|Obligatorisk|
|-|-|-|-|
|idlokalt|Sträng|Inspektionens id i kontrollmyndighetens uppföljningssystem för livsmedelskontroller.|Ja|
|id|Sträng|Ett nationellt **unikt id** för inspektionen, skapas genom att sätta samman kontrollmyndighetens *id* (ifrån *anläggning*) och *idlokalt* med ett understrykningstecken emellan. |Ja|
|anlaggningsid|Sträng|*Id* från anläggningen som har blivit inspekterad (notera att detta *anläggningens* *id* och inte *idlokalt* från *anlaggning* objektet)|Ja|
|datum|Sträng|Datumet då denna inspektion utfördes på formatet YYYY-MM-DD|Ja|
|bedomning|Integer|Bedömningen av inspektonen. Giltiga värden är 0-2: <ul><li>0 = ingen anmärkning</li><li>1 = mindre anmärkning</li><li>2 = större anmärkning</li></ul>Detta är det viktigaste fält för inspektionen då bedöming 2 är en viktig varningsflagga då någon allvarlig avvikelse hittades under inspektionen, vilket användare av applikationer som bygger på denna data bör uppmärksammas på.<br/><br/>Notera att dessa bedömningar är annorlunda än den data som krävs av Livsmedelsverket. Detta dels för att inte denna specification ska vara beroende av Livsmedelsverkets ev. framtida förändringar, dels för att denna data har en annan målgrupp än Livsmedelsverket.  |Ja|

Exempel:

	<inspektioner>
    	<inspektion>
			<idlokalt>8171</idlokalt>
			<id>1280_8171</id>
			<anlaggningsid>1280_123</anlaggningsid>
			<datum>2016-05-26</datum>
			<bedomning>1</bedomning>		
		</inspektion>
		<inspektion>
			<idlokalt>123</idlokalt>
			<id>1280_123</id>
			<anlaggningsid>1280_987</anlaggningsid>
			<datum>2016-04-12</datum>			
			<bedomning>2</bedomning>
		</inspektion>
		<inspektion>
			...
		</inspektion>
		...
	</inspektioner>
