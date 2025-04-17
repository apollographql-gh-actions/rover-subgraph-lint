# Apollo Rover Subgraph Lint

**IMPORTANT**: This action requires that you first install Rover into the PATH. To do so, please use the [`install-rover` GitHub Action](https://github.com/apollographql-gh-actions/install-rover) as shown below.

This is a GitHub Action to perform the [`rover subgraph lint`](https://www.apollographql.com/docs/rover/commands/subgraphs#subgraph-lint) command.

## Inputs

| Name                              | Description                                                                | Required | Default |
| --------------------------------- | -------------------------------------------------------------------------- | :------: | :-----: |
| `apollo-key`                      | Your Apollo Studio API key                                                 |    *     |         |
| `graph-ref`                       | `<NAME>@<VARIANT>` of graph in Apollo Studio                               |    *     |         |
| `name`                            | The name of the subgraph                                                   |    *     |         |
| `schema`                          | The schema file to check                                                   |    *     |         |
| `ignore-existing-lint-violations` | Set to `true` if the check should ignore existing violations               |          | `false` |
| `log`                             | Specify Rover's log level                                                  |          | `info`  |
| `format`                          | Specify Rover's log format type [`plain`, `json`]                          |          | `plain` |
| `client-timeout`                  | Configure the timeout length (in seconds) when performing HTTP(S) requests |          |  `30`   |

## Usage

_**Note**: You must first install the Rover CLI_

```yaml
- uses: apollographql-gh-actions/install-rover@v1
- uses: apollographql-gh-actions/rover-subgraph-lint@v1
  with:
    apollo-key: ${{ secrets.APOLLO_KEY }}
    graph-ref: ${{ vars.APOLLO_GRAPH_REF }}
    name: subgraph-name
    schema: ./path/to/schema.graphql
```
