
# Cadeias MCMC: Curvatura Espacial e Energia Escura Dinâmica

Este repositório contém as cadeias MCMC, os arquivos de configuração (`.yaml`) e os scripts de análise utilizados no Trabalho de Conclusão de Curso (TCC) de **Gabriel Augusto Gonçalves Ismerim**, defendido no Departamento de Física da Universidade Federal de Sergipe (UFS) em 2026.

**Orientador:** Prof. Javier Ernesto Gonzalez Sanchez

---

## 🇧🇷 Português (Principal)

### 📊 Modelos Analisados
As cadeias foram geradas utilizando o código **Cobaya** (com o **CAMB** para as previsões teóricas) e analisadas com o pacote **GetDist**. Foram testados quatro modelos cosmológicos:
*   **ΛCDM**: Modelo padrão (universo plano, energia escura constante com *w* = -1).
*   **oΛCDM**: Extensão com curvatura espacial livre (Ω<sub>k</sub> ≠ 0).
*   **CPL**: Extensão com energia escura dinâmica (*w(a)* = *w*<sub>0</sub> + *w*<sub>a</sub>(1 - *a*)).
*   **oCPL**: Extensão combinando curvatura livre e energia escura dinâmica.

### 📁 Dados Observacionais (Likelihoods)
As cadeias foram restringidas utilizando a combinação dos seguintes dados:
*   **CMB:** Planck PR4 (CamSpec NPIPE) + CMB Lensing.
*   **Supernovas Tipo Ia:** Pantheon+.
*   **BAO:** DESI DR2.

### 📂 Estrutura do Repositório
*   `chains/CPL/`: Contém as pastas `CPL 2025` e `oCPL 2025` com as cadeias MCMC, matrizes de covariância (`.covmat`), arquivos de configuração (`.yaml`) e *trace plots*.
*   `chains/LCDM/`: Contém as pastas `LCDM 2024`, `LCDM 2025`, `oLCDM 2025 2` e `oLCDM 2025`.

### 🚀 Como utilizar os dados (Python)
Para carregar as cadeias e gerar gráficos (como o *triangle plot*), recomenda-se o uso da biblioteca `getdist`.

1. Instale as dependências:
   ```bash
   pip install getdist numpy matplotlib
   ```
2. Exemplo de código para carregar a cadeia do modelo CPL:
   ```python
   from getdist import loadMCSamples, plots
   import os

   # Caminho para a pasta da cadeia
   pasta_cpl = 'chains/CPL/CPL 2025/CPL'

   # Carregando as amostras (o GetDist ignora os números .1, .2, etc automaticamente)
   samples = loadMCSamples(pasta_cpl)

   # Gerando e salvando o triangle plot
   g = plots.get_subplot_plotter()
   g.triangle_plot([samples], filled=True)
   g.export('triangle_cpl.png')
   ```

---

## 🇬🇧 English (Complement)

This repository contains the MCMC chains, configuration files, and analysis scripts used in the BSc thesis of **Gabriel Augusto Gonçalves Ismerim** at the Federal University of Sergipe (UFS), Brazil (2026).

### Models
MCMC chains were generated using **Cobaya** (with **CAMB**) and analyzed with **GetDist** for:
*   **ΛCDM** (Standard)
*   **oΛCDM** (Free spatial curvature)
*   **CPL** (Dynamical dark energy)
*   **oCPL** (Curvature + Dynamical dark energy)

### Datasets
*   **CMB:** Planck PR4 (CamSpec NPIPE) + Lensing
*   **Supernovae:** Pantheon+
*   **BAO:** DESI DR2

### Usage
Use the `getdist` Python package to load the chains. Example:
```python
from getdist import loadMCSamples
samples = loadMCSamples('chains/CPL/CPL 2025/CPL')
```

---

## 📝 Citação / Citation
Se utilizar estes dados ou scripts, por favor cite / If you use these data or scripts, please cite:

> ISMERIM, G. A. G. *Curvatura Espacial e Energia Escura Dinâmica: extensões do modelo padrão da cosmologia*. 2026. Trabalho de Conclusão de Curso – Universidade Federal de Sergipe, São Cristóvão, 2026.

## 📄 Licença / License
Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.
