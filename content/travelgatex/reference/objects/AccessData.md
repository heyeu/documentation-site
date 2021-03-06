{
  "title": "AccessData",
  "description": "",
  "weight": 1,
  "fields": [
    {
      "typeString": "String!",
      "name": "name",
      "url": "/travelgatex/reference/scalars/string",
      "description": "Access descriptive name",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "Boolean!",
      "name": "isActive",
      "url": "/travelgatex/reference/scalars/boolean",
      "description": "Indicates if the access is active.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "ID!",
      "name": "code",
      "url": "/travelgatex/reference/scalars/id",
      "description": "Unique AccessConfiguration identifier",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "Supplier!",
      "name": "supplier",
      "url": "/travelgatex/reference/objects/supplier",
      "description": "supplier for this access.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "Boolean!",
      "name": "isTest",
      "url": "/travelgatex/reference/scalars/boolean",
      "description": "Indicates if this access can be used for testing or not",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "String",
      "name": "user",
      "url": "/travelgatex/reference/scalars/string",
      "description": "User code to connect to supplier.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "String",
      "name": "password",
      "url": "/travelgatex/reference/scalars/string",
      "description": "Password for the connection.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "Urls",
      "name": "urls",
      "url": "/travelgatex/reference/objects/urls",
      "description": "Specific Urls",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "[Parameter]",
      "name": "parameters",
      "url": "/travelgatex/reference/objects/parameter",
      "description": "List of parameters for additional information.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "[String!]",
      "name": "markets",
      "url": "/travelgatex/reference/scalars/string",
      "description": "Markets allowed for the access.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "[RateRulesType!]",
      "name": "rateRules",
      "url": "/travelgatex/reference/enums/raterulestype",
      "description": "Business rules types for the access.",
      "isDeprecated": false,
      "args": null
    },
    {
      "typeString": "Access",
      "name": "shared",
      "url": "/travelgatex/reference/objects/access",
      "description": "Parent access if Shared access",
      "isDeprecated": false,
      "args": null
    }
  ],
  "deprecatedFields": null,
  "requireby": [
    {
      "name": "Access",
      "description": "",
      "url": "/travelgatex/reference/objects/access"
    }
  ],
  "enumValues": null,
  "operator": "type",
  "typename": "AccessData"
}
## GraphQL Schema definition

{{% graphql-schema-type %}}

## Fields

{{% graphql-field %}}

## Require by

{{% graphql-require-by %}}
