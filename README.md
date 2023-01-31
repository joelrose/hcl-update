# HCL Update

A small GitHub Action composite which can update a resource attribute in HCL in another repository.

## Usage

See [action.yml](action.yml)

**Basic Infrastructure example:**

```yaml
steps:
- uses: joelrose/hcl-update@v0.2
  with:
    gh-token: ${{ secrets.GH_TOKEN }}
    variable: "variable.image_hash.default"
    value: ${{ GITHUB_SHA }}
    repository: "github.com/joelrose/infrastructure" 
    file-path: "variables.tf"
    git-commit-message: "automated: deploy xxx service"
    git-branch-name: "automated/${GITHUB_SHA}"
```
