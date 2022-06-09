# Change and Commit Yaml

This Action clones a repository, then changes a Yaml file inside it and pushes the changes.

## Example

A simple usage:

```yaml
steps:
    - uses: actions/checkout@v3

    - uses: sumup-bank/run-credo@v1
      with:
        filepath: helm/chart/values.yaml
        yamlpath: server.images.tag
        newvalue: ${{ steps.generate-new-version.outputs.version-tag }}
```
## Inputs

|Variable|Description|Default|Required|
|-|-|-|-|
|filepath|Path to Yaml file to be changed|N/A|Yes|
|yamlpath|Yaml path to the key that will have its value changed|N/A|Yes|
|newvalue|New value to be inserted at `yamlpath`|N/A|Yes|

## Outputs

None
