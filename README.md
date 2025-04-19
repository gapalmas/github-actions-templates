# ♻️ GitHub Actions Reusables - Seguridad de Código y Contenedores

Este repositorio contiene **workflows reutilizables de GitHub Actions** diseñados para escaneo de vulnerabilidades y análisis de seguridad:

- 🔐 **CodeQL** para análisis estático del código fuente.
- 🐳 **Trivy** para escaneo de imágenes Docker.

## ✅ Uso de workflows reutilizables

### 🔐 CodeQL Analysis examples

```yaml
jobs:
  codeql:
    uses: gapalmasss/github-actions-templates/.github/workflows/codeql-analysis.yml@main
    with:
      language: 'python'
```

### 🐳 Trivy Docker Scan examples

```yaml
jobs:
  trivy:
    uses: gapalmasss/github-actions-templates/.github/workflows/trivy-scan.yml@main
    with:
      image-name: 'gapalmasss/html_to_pdf'
      image-tag: '${{ github.sha }}'
      severity: 'CRITICAL,HIGH'
      output-format: 'sarif'
```

## 🧩 Licencia

MIT © [gapalmas](https://github.com/gapalmas)