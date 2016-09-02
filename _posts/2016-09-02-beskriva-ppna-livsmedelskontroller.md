---
layout: page
title: "Beskriva öppna livsmedelskontroller"
category: doc
date: 2016-09-02 14:03:20
order: 4
---
De öppna livsmedelskontroller som publiceras enligt denna specifikation och beskrivs med DCAT-AP bör taggas med (dvs ha DCAT-AP *keyword*) *livsmedelskontroll2016*. Detta gör det möjligt att hitta alla livsmedelskontroller som följer denna specifikation på öppna data portaler som tex öppnadata.se.

Om det finns behov att beskriva var man kan hitta öppna livsmedelskontroller från flera olika parter så bör detta göras i följande format...

    <livsmedelskontroller>
    	<livsmedelskontroll>
            <anlaggningar>URL till anlaggningar.xml</anlaggningar>
    		<inspektioner>URL till inspektioner.xml</inspektioner>
    	</livsmedelskontroll>
    	<livsmedelskontroll>
    		...
    	</livsmedelskontroll>
    </livsmedelskontroller>
    
Detta kan tex göras av leverantörerna av livsmedelskontrollsystem för att lista alla kommuner som använder deras system och publicerar öppna livsmedelskontroller.