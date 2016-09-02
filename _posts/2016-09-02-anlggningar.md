---
layout: page
title: "Anläggningar"
category: doc
date: 2016-09-02 14:02:45
order: 2
---
En *anläggning* i denna specifikation är den plats som inspekteras av livsmedelsinspektörer, tex en restaurang eller storkök. Alla anläggningar beskrivs med ett *anlaggning* objekt som innehåller data om anläggningens namn, id, adress, position och typ samt vem det är som är ansvarig för att inspektera anläggningen. Många *anlaggning* objekt listas i ett *anlaggningar* objekt. 

Rekommendationen är att inte lista anläggningar som är *"vilande"* eller *"upphörda"*, dvs som ej längre aktivt inspekteras av olika anledningar (tex om det har varit ägarbyte).  

|Attribut|Typ|Beskrivning|Obligatorisk|
|-|-|-|-|
|idlokalt|Sträng|Anläggningens id i kontrollmyndighetens uppföljningssystem för livsmedelskontroller.|Ja|
|id|Sträng|Ett nationellt **unikt id** för anläggningen, skapas genom att sätta samman kontrollmyndighetens *id* (se nedan) och *idlokalt* med ett understrykningstecken emellan. |Ja|
|kontrollmyndighet|Objekt|Myndighet ansvarig för anläggningens livsmedelskontroller|Ja|
|kontrollmyndighet > id|Sträng|Id enligt [SCBs regionala indelningar](http://www.scb.se/sv_/Hitta-statistik/Regional-statistik-och-kartor/Regionala-indelningar/Lan-och-kommuner/Lan-och-kommuner-i-kodnummerordning/), tex *1280* för Malmö.|Ja|
|kontrollmyndighet > namn|Sträng|Namnet på kontrollmyndigheten|Ja|
|namn|Sträng|Namnet på anläggningen (dvs namnet som står på restaurangens dörr)|Ja|
|typ|Integer|Typ av anläggning. Giltiga värden 1-10:<ul><li>1 = Industri - tex charketurifabriker, fiskanläggningar, matindustrier och stora bagerier</li><li>2= Partihandel</li><li>3= Restaurang</li><li>4= Pizzeria</li><li>5= Cafe</li><li>6 = Gatukök</li><li>7 = Skola/förskola</li><li>8= Vård/omsorg</li><li>9 = Food Truck - rörliga matvagnar</li><li>10 = Övrigt - tex vattenverk, dricksvattenanläggningar eller apotek</li></ul> Notera att dessa typer är annorlunda än de som krävs av Livsmedelsverket. Detta dels för att inte denna specification ska vara beroende av Livsmedelsverkets ev. framtida förändringar, dels för att denna data har en annan målgrupp än Livsmedelsverket. |Ja|
|adress|Objekt|Anläggningens adress. Notera att denna data ibland inte är kvalitetssäkrad, dvs kan vara missvisande eller inkorrekt.|Nej, men starkt rekommenderad. Bör anges i alla fall förutom då adressinformation helt saknas, tex för mobila enheter (dvs typ = 9).|
|adress > gatuadress|Sträng|Anläggningens gatuadress, inkl gatunummer|Ja (om adress anges)|
|adress > postort|Sträng|Anläggningens postort|Ja (om adress anges)|
|adress > postnummer|Sträng|Anläggningens postnummer|Ja (om adress anges)|
|orgnr|Sträng|Organisationsnummer på den organisation som äger anläggningen|Nej|
|koordinater|Objekt|Anläggningens geografiska koordinater|Nej|
|koordinater > system|Integer|Vilket koordinatsystem som long/lat anges i enligt ESPG. Exempelvis så är WGS84 = 4326 och RT90 = 4124|Ja (om *koordinater* anges)|
|koordinater > long|Sträng|Anläggningens longitud i det angivna koordinatsystemet. Ska anges med punkt som kommaseparator|Ja (om *koordinater* anges)|
|koordinater > lat|Sträng|Anläggningens latitud i det angivna koordinatsystemet. Ska anges med punkt som kommaseparator|Ja (om *koordinater* anges)|
|uppdaterad|Sträng|Datum på formatet YYYY-MM-DD när någon av den information om anläggningen som listas i denna spec har uppdaterats|Nej|

Exempel:

	<anlaggningar>    
    	<anlaggning>
	    	<idlokalt>123</idlokalt>
	    	<uniktid>1280_123</uniktid>
	    	<kontrollmyndighet>
		    	<id>1280</id>
		    	<namn>Malmö kommun</namn>
	    	</kontrollmyndighet>
	    	<namn>Foo Bar</namn>
	    	<typ>3</typ>
	    	<adress>
		    	<gatuadress>Storgatan 1</gatuadress>
		    	<postort>Malmö</postort>
		    	<postnummer>222 22</postnummer>
	    	</adress>
    	</anlaggning>
    	<anlaggning>
    		...
    	</anlaggning>
    	...
	</anlaggningar>



