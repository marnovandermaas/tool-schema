# Tool version schema

This is a machine and human readable schema for specifying tools in a project.

Tested with [modified ajv](https://github.com/marnovandermaas/ajv-cli).

## Tests:

```
> node ajv-cli/dist/index.js -s tool_schema.hjson -d valid_tool_data.hjson
valid_tool_data.hjson valid
```

```
> node ajv-cli/dist/index.js -s tool_schema.hjson -d invalid_tool_data.hjson
invalid_tool_data.hjson invalid
[
  {
    keyword: 'required',
    dataPath: '[1]',
    schemaPath: '#/items/required',
    params: { missingProperty: 'version' },
    message: "should have required property 'version'"
  }
]
```

## Future work

Use the latest Schema version: 2020-12.

The best way to go is probably to extend [ajv](https://github.com/ajv-validator/ajv-cli) to use the "anyjson" package like pajv does.
