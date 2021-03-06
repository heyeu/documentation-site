+++
title = "Markup"
pagetitle = "Markup"
description = "Markup plugins"
icon = "fa-money"
weight = 3
alwaysopen = false
+++

Markups type plugins permits to apply markup percentages over a price, markup is a field in price composed of a set of rules and a new price with an added percentage, the percentage is the sum of every rule applied.

Although this plugin can be customized, we already offer an implementation.

## MarkupX

This markup implementation is supported by our [web application](https://travelb2b.xmltravelgate.com/) which permits the management of an organization's rules, the modification of these rules are applied in your product at real time.

In this plugin, a rule is a set of criteria with an associated percentage, an option will apply a rule when it matches every rule’s criteria.

The available criteria of a rule are:

* supplier 
* hotel, city or zone 
* board 
* market 
* price range 
* cancellation Policies (refundable or not refundable) 
* rate (b2b or b2c) 
* check in date 
* booking date 
* channel 

Additionally, a rule has an ‘override’ flag that permits it to be the only rule applied (ignoring the rest)  when set to true. We only let a rule to be overriding when it contains at least the criterion: hotel, city or zone. If multiple override rules are valid for an option, the rule with the heavier weight is applied. The hotel criterion is heavier than city, and city is heavier than zone.

### Parameters

|key|value type|condition|description|
|----|----|----|----|
|channel|string|optional|channel is a rule criterion|
|applyNegativeCom|bool|optional|if not set or set to false, if the sum of rules percentages is negative the percentage won’t apply|
|rules|json|optional|an array of rules in json is expected, if found, those rules will apply to each option, doesn’t matter if an option matches the criteria, it will have the rules applied|

### Files Format

In order to manage city and zone criteria, a previous batch load must be done to make a relation with hotel codes.

Two file are needed:

#### From hotel code to his minimum city code:

* **Encoding**: UTF-8 
* **File Name**: [Context Source]\_Porfolio.csv 
* **Header Row**: HotelCode, CityCode
* **Delimiter**:  Comma (“,”) 
* **Directory**: ftp://ftp.xmltravelgate.com/Purchasing/Markup 

#### Destination trees:

* **Encoding**: UTF-8 
* **File Name**: [Context Source]\_DestinationsTree.csv 
* **Header Row**: DestinationCode, ParentCode, ISOCountryCode 
* **Delimiter**:  Comma (“,”) 
* **Directory**: ftp://ftp.xmltravelgate.com/Purchasing/Markup 

### Execution example

```
{

    "plugins": {

        "step": "RESPONSE\_OPTION",

        "pluginsType": [

            {

                "type": "MARKUP"

                "name": "markupX",

                "parameters": [

                    {

                        "key": "channel",

                        "value": "1000"

                    },

                    {

                        "key": "applyNegativeCom",

                        "value": "true"

                    }

                ]

            }

        ]

    }

}
```
