# Actions

Reusable GitHub Actions

# `setup-pre-commit-uv`

Install [`pre-commit`][pre-commit] using [`uv`][uv], init it and setup caching

All inputs are optional.

```yaml
# default values of all inputs
- name: Setup pre-commit
  uses: muzimuzhi/actions/setup-pre-commit-uv@main
  with:
    setup-uv: true
    version: 'latest'
    config: '.pre-commit-config.yaml'
    run-pre-commit: true
    args: '--all-files --show-diff-on-failure --color=always'
```

`uv` cache is disabled by default ([why][why-disable-uv-cache]). If needed,
setup `uv` beforehand, then use this action with `setup-uv: false`.

```yaml
- name: Setup uv
  uses: astral-sh/setup-uv@v6
  with:
    enable-cache: true # enabled on GitHub-hosted runners by default

- name: Setup pre-commit
  uses: muzimuzhi/actions/setup-pre-commit-uv@main
  with:
    setup-uv: false
```

[pre-commit]: https://github.com/pre-commit/pre-commit
[uv]: https://github.com/astral-sh/uv
[why-disable-uv-cache]: https://github.com/astral-sh/setup-uv/tree/v6/?tab=readme-ov-file#disable-cache-pruning

# `ppmcheckpdf-deps`

Install dependencies for [`ppmcheckpdf`](https://ctan.org/pkg/ppmcheckpdf)
LaTeX package or the [`ppmcheckpdf.lua`][ppmcheckpdf.lua] in
`muzimuzhi/latex-zutil` repository.

[ppmcheckpdf.lua]: https://github.com/muzimuzhi/latex-zutil/blob/main/support/ppmcheckpdf.lua
