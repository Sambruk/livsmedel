---
layout: page
title: "Exempel med JSON"
category: doc
date: 2020-10-21 09:55:00
order: 3
---
Nedan visas ett exempel över hur den här informationen skulle se ut i ett JSON-format:

```
{
  "lang": "sv",
  "generator": "Castor",
  "inspecOrg": {
    "name": "Malmö stad",
    "id": "1280",
    "sweref99local": "SWEREF 99 15 00"
  },
  "facilities": [
    {
      "organizationNumber": "1655112233",
      "name": "Pizzeria Vesuvio",
      "type": [
        "Livsmedelstillverkning",
        "Produktion av animaliska livsmedel",
        "Fiskanläggningar",
        "Helkonservering (steril)"
      ],
      "expClass": "A",
      "riskClass": "Riskklass 5", 
      "inspecTime": "12",
      "idLocal": "14",
      "idNational": "F-1280-14",
      "active": "2",
      "created": "2018-05-10T12:31:57+01:00",
      "modified": "2020-03-19T16:31:34+01:00",
      "address": {
        "streetAddress": "Stortorget 12",
        "postalCode": "38782",
        "locality": "Malmö",
        "region": "Skåne",
        "country": "SE"
      },
      "location": {
        "wgs84": {
          "type": "Point",
          "coordinates": [
            55.606160,
            13.000366
          ]
        },
        "sweref99": {
          "type": "Point",
          "coordinates": [
            6164061.848,
            374031.174
          ]
        },
        "sweref99local": {
          "type": "Point",
          "coordinates": [
            6164061.848,
            374031.174
          ]
        }
      }
    }
  ],
  "inspections": [
    {
      "idLocal": "1",
      "idNational": "I-1280-1",
      "prenotified": true,
      "type": 0,
      "inspectionPoints": {
        "passed": [
          "A01", "J02"
        ],
        "remark": [
          "A03", "J07"
        ]
      },
      "assessment": 0,
      "ownerComment": "",
      "date": "2020-03-19T16:31:34+01:00",
      "modified": "2020-04-13T12:01:04+01:00"
    }
  ]
}
```