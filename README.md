# find-pull-request-action

A GitHub Action for finding pull requests.

## Usage

```yaml
steps:
  - name: Find Pull Request
    uses: ThiagoDallacqua/find-pull-request-action@v1
    id: find-pull-request
    with:
      branch: my-branch-name
      branch-special-token: anything that might be in the branch name (to be used by companies that has complext branching rules)
  - run: echo "Pull Request ${number} (${sha})"
    env:
      number: ${{ steps.find-pull-request.outputs.number }}
      sha: ${{ steps.find-pull-request.outputs.head-sha }}
```

Query pull requests based on these inputs:
- `branch`
- `base`
- `author`
- `state`
- `repo`
- `sort`
- `direction`
- `labels`

For the first matching pull request, these outputs will be set:
- `number`
- `title`
- `url`
- `head-ref`
- `head-sha`
- `base-ref`
- `base-sha`
- `base-repo`
- `state`

See [action.yml](action.yml) for more details.

## License

MIT
