# European Union

Implements fields and codes that are specific to European law.

For complete guidance on meeting the disclosure requirements of European law, see [OCDS for European Union](https://standard.open-contracting.org/profiles/eu/master/en/).

## Legal context

In the European Union, this extension's fields correspond to [eForms BT-10 and BT-610](https://github.com/eForms/eForms). See [OCDS for the European Union](http://standard.open-contracting.org/profiles/eu/master/en/) for the correspondences to Tenders Electronic Daily (TED).

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
    "valueCalculationMethod": "Income from the sales of tickets over the duration of the contract minus the fees paid to the procuring entity."
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
  ]
}
```

## Issues

Report issues for this extension in the [ocds-extensions repository](https://github.com/open-contracting/ocds-extensions/issues), putting the extension's name in the issue's title.

## Changelog

This extension was originally discussed as part of the [OCDS for EU profile](https://github.com/open-contracting-extensions/european-union/issues) and in [pull requests](https://github.com/open-contracting-extensions/ocds_eu_extension/pulls?q=is%3Apr+is%3Aclosed).
