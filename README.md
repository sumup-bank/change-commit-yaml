# Change and Commit Yaml

This Action clones a repository, then changes a Yaml file inside it and pushes the changes.

**Note:** this actions uses [mikefarah/yq](https://github.com/mikefarah/yq), which you may access the README to gather more information on how to write the `yamlpath` inputs.

## Example

A simple usage:

```yaml
steps:
    - uses: actions/checkout@v3

    - uses: sumup-bank/run-credo@v1
      with:
        repository: sumup/yaml-files
        filepath: helm/chart/values.yaml
        yamlpath: .a.b[0].c
        newvalue: ${{ steps.generate-new-version.outputs.version-tag }}
```
## Inputs

|Variable|Description|Default|Required|
|-|-|-|-|
|repository|The repository to clone and then push|N/A|Yes|
|ref|The branch, tag or SHA to checkout|The repository branch|Yes|
|filepath|Path to Yaml file to be changed|N/A|Yes|
|yamlpath|Yaml path to the key that will have its value changed|N/A|Yes|
|newvalue|New value to be inserted at `yamlpath`|N/A|Yes|

## Outputs

None
