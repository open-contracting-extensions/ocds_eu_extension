# European Union

Implements fields and codes that are specific to European law.

For complete guidance on meeting the disclosure requirements of European law, see [OCDS for European Union](https://standard.open-contracting.org/profiles/eu/master/en/).

## Guidance

If items have at most one delivery address, use the [Location](https://extensions.open-contracting.org/en/extensions/location/) extension instead ([see discussion](https://github.com/open-contracting/ocds-extensions/issues/115)).

## Legal context

In the European Union, this extension's fields correspond to [eForms BT-99 (Review Deadline Description), BT-163 (Concession Value Description), BT-109 (Framework Duration Justification), BT-505 (Organisation Internet Address), BT-508 (Buyer Profile URL) and BG-708 (Place of Performance)](https://github.com/eForms/eForms). See [OCDS for the European Union](http://standard.open-contracting.org/profiles/eu/master/en/) for the correspondences to Tenders Electronic Daily (TED).

## Example

```json
{
  "parties": [
    {
      "details": {
        "url": "https://www.manchester.ac.uk/",
        "buyerProfile": "https://in-tendhost.co.uk/universityofmanchester/aspx/Home"
      }
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
          "name": "Farida Howard",
          "email": "fhoward@manchester.edu.uk",
          "telephone": "44 (0)1234 56789"
        }
      }
    ],
    "milestones": [
      {
        "id": "1",
        "type": "securityClearanceDeadline",
        "dueDate": "2020-11-19T00:00:00Z"
      }
    ]
  },
  "awards": [
    {
      "id": "award-1",
      "valueCalculationMethod": "The awarded value takes into account the growing revenue expected from fees and the value of the equipment provided by the contracting authority."
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
  "lots": [
    {
      "id": "lot-1",
      "minimumValue": {
        "amount": "12000",
        "currency": "EUR"
      }
    }
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

### 2020-10-05

* add `minimumValue` field to `Lot`.

### 2020-07-13

* Add 'securityClearanceDeadline' code to `+milestoneType.csv` codelist

### 2020-04-29

* Add `Item.deliveryAddresses` field

### 2020-04-24

* Add `minProperties`, `minItems` and/or `minLength` properties

This extension was originally discussed as part of the [OCDS for EU profile](https://github.com/open-contracting-extensions/european-union/issues), in [this issue](https://github.com/open-contracting/european-union-support/issues/19) and in [pull requests](https://github.com/open-contracting-extensions/ocds_eu_extension/pulls?q=is%3Apr+is%3Aclosed).
