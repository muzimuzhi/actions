# Actions

Reusable GitHub Actions

# `setup-pre-commit-uv`

Install `pre-commit` using `uv`, init it and setup caching

All inputs are optional.

```yaml
# default values of all inputs
- name: Setup pre-commit
  uses: muzimuzhi/actions/setup-pre-commit-uv@main
  with:
    uv-if-setup: true
    version: 'latest'
    config-path: '.pre-commit-config.yaml'
    if-run: true
    run-args: '--all-files --show-diff-on-failure --color=always'
```

If `uv` cache is needed, set `uv-if-setup: false` and setup `uv` manually.

```yaml
- name: Setup uv
  uses: astral-sh/setup-uv@v6
  with:
    enable-cache: true # enabled on GitHub-hosted runners by default

- name: Setup pre-commit
  uses: muzimuzhi/actions/setup-pre-commit-uv@main
  with:
    uv-if-setup: false
```
