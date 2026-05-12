# Auditoria de Dados — Portal da Transparência Federal

Simulação de trabalho de auditoria de dados sobre despesas com diárias e passagens de servidores públicos federais (2022–2024), utilizando dados públicos da API do Portal da Transparência. O projeto aplica metodologia de auditoria baseada no framework COSO e técnicas de análise de dados em Python.

---

## Contexto

Auditorias de dados são parte central do trabalho de firmas de auditoria e consultoria de risco. Este projeto simula, de ponta a ponta, como um analista de auditoria de tecnologia estruturaria um trabalho real: do planejamento e avaliação de riscos até a execução de testes automatizados e a elaboração de um relatório de achados.

A fonte de dados é pública e oficial — a [API do Portal da Transparência](https://api.portaldatransparencia.gov.br/) do Governo Federal, que disponibiliza informações sobre gastos, servidores e contratos da administração pública federal.

---

## Objetivos de Auditoria

| Dimensão | Pergunta central |
|---|---|
| **Completude** | Todos os registros possuem campos obrigatórios preenchidos? |
| **Exatidão** | Os valores estão dentro dos limites legais por cargo e destino? |
| **Conformidade** | Os pagamentos seguem as normas do Decreto nº 5.992/2006? |

---

## Estrutura do Repositório

```
auditoria-transparencia-federal/
│
├── docs/
│   ├── 01_planejamento_auditoria.md   # Escopo, riscos e metodologia
│   └── metodologia.md                 # COSO e COBIT aplicados ao projeto
│
├── notebooks/
│   ├── 01_coleta.ipynb                # Conexão e extração via API
│   ├── 02_qualidade.ipynb             # Testes de completude e validade
│   ├── 03_testes_auditoria.ipynb      # Detecção de anomalias e outliers
│   └── 04_visualizacoes.ipynb         # Gráficos e painel de achados
│
├── data/
│   ├── raw/                           # Dados brutos extraídos da API
│   └── processed/                     # Dados tratados para análise
│
├── relatorio/
│   └── relatorio_auditoria_final.pdf  # Relatório de achados no formato Big Four
│
├── dashboard/
│   └── dashboard.pbix                 # Painel Power BI (ou app Dash)
│
├── requirements.txt
└── README.md
```

---

## Metodologia

O trabalho foi estruturado em cinco fases, seguindo o processo padrão de auditoria:

```
Fase 1 — Planejamento       Escopo, matriz de riscos, referência normativa
Fase 2 — Coleta de Dados    Extração via API, tratamento e documentação
Fase 3 — Testes             Procedimentos analíticos e testes automatizados
Fase 4 — Visualização       Dashboard de achados e painel de anomalias
Fase 5 — Relatório          Achados, avaliação de risco e recomendações
```

**Frameworks de referência:** COSO (2013) · COBIT 2019

---

## Principais Achados

> Os achados detalhados estão no [relatório final](relatorio/relatorio_auditoria_final.pdf).

| # | Achado | Risco | Registros afetados |
|---|---|---|---|
| A01 | Pagamentos com CPF, valor e data idênticos | Alto | — |
| A02 | Valores acima do teto legal de diárias | Alto | — |
| A03 | Campos obrigatórios ausentes (CPF ou destino) | Médio | — |
| A04 | Viagens registradas em fins de semana | Médio | — |
| A05 | Outliers estatísticos (Z-score > 3σ) | Médio | — |

*Os campos de quantidade serão preenchidos ao final da Fase 3.*

---

## Tecnologias Utilizadas

| Ferramenta | Uso |
|---|---|
| Python 3.11 | Coleta, limpeza e testes de auditoria |
| Pandas / NumPy | Manipulação e análise de dados |
| SciPy | Detecção de outliers (Z-score) |
| Plotly / Dash | Visualizações interativas |
| Power BI | Dashboard executivo |
| Jupyter Notebook | Documentação dos procedimentos |
| API Portal da Transparência | Fonte de dados oficial |

---

## Como Reproduzir

**1. Clone o repositório**
```bash
git clone https://github.com/seu-usuario/auditoria-transparencia-federal.git
cd auditoria-transparencia-federal
```

**2. Instale as dependências**
```bash
pip install -r requirements.txt
```

**3. Configure o acesso à API**

Cadastre-se gratuitamente em [portaldatransparencia.gov.br/api-de-dados](https://portaldatransparencia.gov.br/api-de-dados) e obtenha sua chave de acesso. Crie um arquivo `.env` na raiz do projeto:

```
API_KEY=sua_chave_aqui
```

**4. Execute os notebooks em ordem**
```
notebooks/01_coleta.ipynb → 02_qualidade.ipynb → 03_testes_auditoria.ipynb → 04_visualizacoes.ipynb
```

---

## Referência Normativa

- **Decreto nº 5.992/2006** — Regulamenta concessão de diárias no âmbito federal
- **Portaria MPOG nº 505/2009** — Tetos de diárias por categoria de servidor
- **COSO (2013)** — Framework de controle interno
- **COBIT 2019** — Governança e gerenciamento de TI (ISACA)

---

## Sobre o Projeto

Este projeto foi desenvolvido como parte de um portfólio para a área de **Auditoria de Tecnologia / Data & Analytics**, com foco em demonstrar capacidade de estruturar e executar um trabalho de auditoria de dados de forma independente, combinando:

- Pensamento orientado a riscos e controles
- Capacidade analítica e uso de dados públicos
- Documentação profissional no padrão de firmas de auditoria

---

## Autor

**Rafael Rachidi da Rocha**  
www.linkedin.com/in/rafael-rachidi-851016308
