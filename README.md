# check-tag-existence
A simple github action to check for the existence of a git tag. If the specified tag doesn't exist, the workflow is failed.

# Usage
Include the action as a step in your workflow. The worklfow will proceed if the tag exists otherwise it will be failed

```yaml
  pre-deploy-prod:
    name: Prod - Deploy Checks
    if: (github.event_name=='workflow_dispatch')
    runs-on: [ self-hosted, linux, X64 ]
    steps:
      - name: check tag
        id: check-tag
        uses: delfidiagnostics/check-tag-existence@v1.1
        with:
          tag: ${{inputs.tag}}
```