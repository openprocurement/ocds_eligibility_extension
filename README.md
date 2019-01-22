## Eligible
This extension introduces three fields that can be used to 
show compliance of eligibility criteria in the tender documents.
## Overview
The fields introduced by this extension are:
- `awards/eligible` - The boolean value which confirms compliance of eligibility 
criteria set by the procuring entity in the tendering documents.
- `bids/selfEligible` - The boolean value which confirms compliance of 
eligibility criteria set by the customer in the tendering documents.
- `bids/eligibilityDocuments` - The array of Document objects which shows 
documents related to eligibility of bids.
## Example
The following extract illustrates `eligible` property in use within the `awards` block.
```
{
    "awards": [
        {
          "id": "ocds-213czf-000-00001-award-01",
          "title": "Award of contract to build new cycle lanes in the centre of town.",
          "description": "AnyCorp Ltd has been awarded the contract to build new cycle lanes in the centre of town.",
          "status": "active",
          "date": "2010-05-10T10:30:00Z",
          "value": {
            "amount": 11000000,
            "currency": "GBP"
          },
          "eligible": true,
          "suppliers": [
            {
              "id": "GB-COH-1234567844",
              "name": "AnyCorp Cycle Provision"
            }
          ],
          "contractPeriod": {
            "startDate": "2010-07-01T00:00:00Z",
            "endDate": "2011-08-01T23:59:00Z"
          },
          "documents": [
            {
              "id": "0007",
              "documentType": "notice",
              "title": "Award notice",
              "description": "Award of contract to build new cycle lanes in the centre of town to AnyCorp Ltd.",
              "url": "http://example.com/tender-notices/ocds-213czf-000-00001-04.html",
              "datePublished": "2010-05-10T10:30:00Z",
              "format": "text/html",
              "language": "en"
            }
          ]
        }
    ],
}
```
The following extract shows `selfEligible` and `eligibilityDocuments` 
properties in use within the `bids` block.
```
{
    "bids": {
        "statistics": [
          {
            "id": "1.0",
            "measure": "validBids",
            "value": 1,
            "date": "2016-12-09T01:00:00+01:00",
            "notes": "This statistic covers the total number of unique bids received that were considered valid against relevant criteria."
          }
        ],
        "details": [
          {
            "id": "1.0",
            "date": "2016-12-09T01:00:00+01:00",
            "status": "valid",
            "value": {
              "amount": 1000,
              "currency": "USD"
            },
            "selfEligible": true,
            "eligibilityDocuments": [
              {
                "id": "0007",
                "documentType": "notice",
                "title": "Eligibility Document",
                "description": "Eligibility Document description",
                "url": "http://example.com/tender-eligible/ocds-213czf-000-00001-04.html",
                "datePublished": "2010-05-10T10:30:00Z",
                "format": "text/html",
                "language": "en"
              }
            ],
            "tenderers": [
              {
                "id": "MEGA",
                "name": "Mega Consortium"
              }
            ]
          }
        ]
    },
}
```