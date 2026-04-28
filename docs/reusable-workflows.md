# Reusable Workflows

## Included Workflows
- `.github/workflows/reusable-results-guard.yml`
- `.github/workflows/reusable-pages-smoke.yml`

## Consumer Example
```yaml
name: repo-results-guard

on:
  push:
    branches: [main]
  pull_request:

jobs:
  results:
    uses: ai-webgpu-lab/shared-github-actions/.github/workflows/reusable-results-guard.yml@main
```

```yaml
name: repo-pages-smoke

on:
  workflow_dispatch:

jobs:
  pages:
    uses: ai-webgpu-lab/shared-github-actions/.github/workflows/reusable-pages-smoke.yml@main
    with:
      url: https://ai-webgpu-lab.github.io/exp-llm-chat-runtime-shootout/
      expected_title: exp-llm-chat-runtime-shootout Runtime Readiness Harness
      fallback_query: ?mode=fallback
```
