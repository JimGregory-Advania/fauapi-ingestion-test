1. **Draft Linked API** \
 Required Values:
    -  `autoPublish` - For this scenario auto-publish is not reqiured, therefore it will be set to 'false'.
    -  `displayName` - This value must be between 3 and 100 characters.
    -  `description` - This value must not exceed 40 characters.
    -  `backendType` - There are three available options - http(rest),soap, and graphql. If a different option is given, the specification will fail on validation.
    -  `majorVersion` - This value must not exceed the 50 charachter limit, e.g. 'v1.0'.
    -  `environments` - They are not required for this scenario, therefore the object is left empty. \
    [Example](/json-schemas/linked-apis/examples/example-linked-api-draft.json)
2. **Draft Linked Api + Metadata and Environments** \
    All of the above are also required in this section. The following are also needed:
    -  `overview`: A friendly message that will be presented to the users in the Consumption portal.
    -  `classification` - the API can be cladified as "public", "government", "department".
     -  `visibility` - Allowed values are 'Public', 'DfE Internal', 'Private'".
     -  `tags` - words that are seperetated by semi-colon. They are used to utilise the search of APIs in FaUAPI.
     -  `serviceLevel` - The level of service can be specified here as a short description. This is not a required field
     -  `technology` - what tecnology is used for the development of the API, this is also not required.
     - `usage` - Describe who can use this API. This is also not a required field. \
      [Example](/json-schemas/linked-apis/examples/example-linked-api-draft-with-metadata.json)
3. **Auto Publish Linked API** \
    All the properties from section 1 and 2 are required here as well.
    Required Values:
   - `autoPublish` : for this scenario the is set to true. This will require more properties to be added to validate the specification.
   - `schemaURL` - A valid url of the where the schema of the api is located.
   - `schemaType` - The type of the schema. Valid values are "openapi","openapi+json","wsdl","swagger".
   - `environments` - Allows to have 0 or max 3 environments, with uniquie names - 'live', 'staging' or 'dev'. This means only one environment with these names is allowed.
   - `releases` - At least one release is required. It's IsCurrent flag must be set to true. Otherwise the specification will not validate. \
 [Example](/json-schemas/linked-apis/examples/example-linked-api-publish.json)