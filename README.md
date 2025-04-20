# ♻️ GitHub Actions Templates - Seguridad de Código y Contenedores

Este repositorio contiene **workflows reutilizables de GitHub Actions** diseñados para escaneo de vulnerabilidades y análisis de seguridad:

- 🔐 **CodeQL** para análisis estático del código fuente.
- 🐳 **Trivy** para escaneo de imágenes Docker.

## ✅ Uso de workflows reutilizables

### 🔐 CodeQL Analysis examples
### Cómo usarlo
```yaml
jobs:
  codeql:
    uses: gapalmas/github-actions-templates/.github/workflows/codeql-analysis.yml@main
    with:
      language: 'python'
```

### 🐳 Trivy Docker container Scan examples
### Cómo usarlo
```yaml
jobs:
  trivy:
    uses: gapalmas/github-actions-templates/.github/workflows/trivy-scan.yml@main
    with:
      image-name: 'gapalmasss/html_to_pdf'
      image-tag: '${{ github.sha }}'
      severity: 'CRITICAL,HIGH'
      output-format: 'sarif'
```

## ✅ YAML Lint (Reusable Workflow)

Este workflow permite validar todos los archivos YAML del repositorio que lo consuma, usando [`yamllint`](https://github.com/adrienverge/yamllint).

### Cómo usarlo

```yaml

name: YAML Syntax Validation

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  lint:
    uses: gapalmas/github-actions-templates/.github/workflows/validate-yaml.yml@main
```


## 🧩 Licencia

MIT © [gapalmas](https://github.com/gapalmas)
