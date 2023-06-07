# European Union

Implements fields and codes that are specific to European law.

For complete guidance on meeting the disclosure requirements of European law, see [OCDS for European Union](https://standard.open-contracting.org/profiles/eu/master/en/).

## Guidance

If items have at most one delivery address, use the [Location](https://extensions.open-contracting.org/en/extensions/location/) extension instead ([see discussion](https://github.com/open-contracting/ocds-extensions/issues/115)).

## Legal context

In the European Union, this extension's fields and codes correspond to the following eForms [business terms](https://docs.ted.europa.eu/eforms/latest/reference/business-terms/) and business groups:
* BT-99 (Review Deadline Description)
* BT-163 (Concession Value Description)
* BT-109 (Framework Duration Justification)
* BT-505 (Organisation Internet Address)
* BT-508 (Buyer Profile URL)
* BG-708 (Place of Performance)
* OPT-030 (Provided Service Type)
* OPP-050 (Buyers Group Lead Indicator)
* OPP-051 (Awarding CPB Buyer Indicator)
* OPP-052 (Acquiring CPB Buyer Indicator)
* OPT-170 (Tendering Party Leader)
* BT-723 (Vehicle Category)
* BT-735 (CVD Contract Type)
* OPT-111 (Fiscal Legislation Document ID)
* OPT-112 (Environmental Legislation Document ID)
* OPT-113 (Employment Legislation Document ID)
* OPT-301 (Organization Technical Identifier Reference)
* BT-1252 (Direct Award Justification Previous Procedure Identifier)

For correspondences to eForms fields, see [OCDS for eForms](https://standard.open-contracting.org/profiles/eforms) and for correspondences to Tenders Electronic Daily (TED), see [OCDS for the European Union](http://standard.open-contracting.org/profiles/eu/master/en/).

## Example

```json
{
  "parties": [
    {
      "details": {
        "url": "https://www.manchester.ac.uk/",
        "buyerProfile": "https://in-tendhost.co.uk/universityofmanchester/aspx/Home"
      },
      "roles": [
        "leadBuyer",
        "awardingCentralPurchasingBody",
        "acquiringCentralPurchasingBody",
        "evaluationBody",
        "submissionReceiptBody"
      ]
    },
    {
      "name": "Royal Tax Office",
      "id": "08797655",
      "contactPoint": {
        "name": "Crown Commercial Service",
        "email": "info@crowncommercial.gov.uk",
        "url": "https://www.gov.uk/government/publications/procurement-policy-note-0314-promoting-tax-compliance"
      },
      "roles": [
        "informationService"
      ]
    },
    {
      "roles": [
        "eSender"
      ]
    },
    {
      "roles": [
        "procurementServiceProvider"
      ]
    },
    {
      "roles": [
        "leadTenderer",
        "tenderer"
      ]
    }
  ],
  "tender": {
    "reviewDetails": "NHS Wales Shared Services Partnership on behalf of Cardiff and Vale University Local Health Board will allow a minimum 10 calendar day standstill period between notifying the award decision and awarding the contract.",
    "valueCalculationMethod": "Income from the sales of tickets over the duration of the contract minus the fees paid to the procuring entity.",
    "items": [
      {
        "id": "item-1",
        "description": "Printer ink cartridges",
        "classification": {
          "scheme": "CPV",
          "id": "45233130.0",
          "description": "Office supplies",
          "uri": "http://cpv.data.ac.uk/code-45233130"
        },
        "deliveryAddresses": [
          {
            "streetAddress": "4, North London Business Park, Oakleigh Rd S",
            "locality": "London",
            "region": "London",
            "postalCode": "N11 1NP",
            "countryName": "United Kingdom"
          }
        ]
      }
    ],
    "legislativeReferences": [
      {
        "title": "Direct taxation in the EU",
        "url": "https://eur-lex.europa.eu/summary/chapter/2101.html",
        "informationService": {
          "name": "Royal Tax Office",
          "id": "08797655"
        }
      }
    ],
    "lots": [
      {
        "id": "lot-1",
        "awardPeriod": {
          "durationInDays": 30,
          "startDate": "2020-11-06T00:00:00Z",
          "endDate": "2020-12-06T00:00:00Z"
        },
        "additionalClassifications": [
          {
            "id": "oth-serv-contr",
            "scheme": "eu-cvd-contract-type",
            "description": "Other service contract"
          }
        ]
      }
    ],
    "milestones": [
      {
        "id": "1",
        "type": "securityClearanceDeadline",
        "dueDate": "2020-11-19T00:00:00Z"
      }
    ],
    "documents": [
      {
        "id": "Fiscal1",
        "documentType": "legislation"
      }
    ]
  },
  "awards": [
    {
      "id": "award-1",
      "valueCalculationMethod": "The awarded value takes into account the growing revenue expected from fees and the value of the equipment provided by the contracting authority.",
      "items": [
        {
          "id": "1",
          "additionalClassifications": [
            {
              "scheme": "eu-vehicle-category",
              "id": "n2-n3",
              "description": "Truck (N2-N3)"
            }
          ]
        }
      ]
    }
  ],
  "contracts": [
    {
      "id": "contract-1",
      "periodRationale": "The duration of the contract has been extended to anticipate the exceptional snowfall expected in January.",
      "publicPassengerTransportServicesKilometers": 765,
      "awardID": "award-1"
    }
  ],
  "relatedProcesses": [
    {
      "id": "1",
      "identifier": "123e4567-e89b-12d3-a456-426614174000",
      "scheme": "eu-oj",
      "relationship": [
        "prior"
      ]
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2023-04-19

* Add codes:
  * classificationScheme.csv:
    * 'eu-vehicle-category'
    * 'eu-cvd-contract-type'
  * documentType.csv:
    * 'legislation'
  * partyRole.csv:
    * 'procurementServiceProvider'
    * 'eSender'
    * 'leadBuyer'
    * 'awardingCentralPurchasingBody'
    * 'acquiringCentralPurchasingBody'
    * 'leadTenderer'
    * 'evaluationBody'
    * 'submissionReceiptBody'
  * relatedProcessScheme.csv:
    * 'eu-oj'

### 2022-05-27

* Move `Lot.minimumValue` to the Lots extension as `Lot.minValue`.

### 2021-01-19

* Set the object type of `informationService` to `OrganizationReference`.
* Add 'informationService' code to `+partyRole.csv` codelist.

### 2020-10-06

* Add `Lot.awardPeriod` field.

### 2020-10-05

* Add `Lot.minimumValue` field.

### 2020-07-13

* Add the 'securityClearanceDeadline' code to the `+milestoneType.csv` codelist.

### 2020-04-29

* Add `Item.deliveryAddresses` field.

### 2020-04-24

* Add `minProperties`, `minItems` and/or `minLength` properties.

This extension was originally discussed as part of the [OCDS for EU profile](https://github.com/open-contracting-extensions/european-union/issues), in [this issue](https://github.com/open-contracting/european-union-support/issues/19) and in [pull requests](https://github.com/open-contracting-extensions/ocds_eu_extension/pulls?q=is%3Apr+is%3Aclosed).
