# Tool version schema

This is a machine and human readable schema for specifying tools in a project.

Tested with ajv: `npm install -g ajv-cli`

## Tests:

```
> ajv --spec=draft2020 -s tool_schema.json -d valid_tool_data.json
valid_tool_data.json valid
```

```
> ajv --spec=draft2020 -s tool_schema.json -d invalid_tool_data.json
invalid_tool_data.json invalid
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
