# Planejamento de Auditoria — Portal de Transparência Federal

**Documento:** Fase 1 de 5 — Planejamento  
**Projeto:** Auditoria de Dados · Despesas com Passagens e Diárias  
**Período auditado:** Janeiro/2022 — Dezembro/2024  
**Auditor responsável:** Rafael Rachidi da Rocha  
**Framework de referência:** COSO · COBIT 2019  
**Status:** Em planejamento  
**Versão:** 1.0  
**Data:** 11/05/2026  

---

## 1. Identificação do Projeto

| Campo | Detalhe |
| --- | --- |
| Tipo de auditoria |Auditoria de dados simulada |
| Fonte de dados | API pública — Portal da Transparência (portaldatransparencia.gov.br) |
| Período auditado | Jan/2022 — Dez/2024 | 
| Tipo de despesa | Diárias e passagens de servidores federais | 
| Framework principal | COSO (2013) | 
| Framework complementar | COBIT 2019 |  

---

## 2. Escopo

Esta auditoria abrange as 
**despesas federais com diárias e passagens**
registradas no Portal da 
Transparência entre janeiro de 2022 e dezembro de 2024. O
foco são pagamentos
realizados a servidores
público federais, avaliando a integridade, completude e conformidade dos dados com as normas vigentes (Decreto de nº 5.992/2006 e atualizações posteriores).

### Dentro do escopo

- Pagamentos de diárias a servidores do Poder Executivo Federal
- Pagamentos de passagens aéreas e terrestres a servidores federais
- Todos os órgãos do Poder Executivo registrados na API

### Fora do escopo

- Despesas de empresas estatais e sociedades de economia mista
- Pagamentos a terceirizados e prestadores de serviço
- Viagens de parlamentares e servidores do Legislativo/Judiciário

---
## 3. Objetivos de Auditoria

### 3.1 Completude
Verificar se todos os registros possuem campos obrigatórios preenchidos: CPF do beneficiário, valor, data da viagem, destino e órgão pagador. Identificar e quantificar registros com ausência de dados críticos.

### 3.2 Exatidão
Avaliar se os valores registrados são consistentes com os limites legais por cargo e destino. Detectar outliers estatísticos, arredondamentos suspeitos e discrepâncias em relação à média histórica do período.

### 3.3 Conformidade
Checar aderência às normas
vigentes:
- Teto de diárias por categoria de servidor (conforme Decreto nº 5.992/2006)
- Proibição de diárias em finais de semana sem justificativa formal
- Unicidade de pagamentos (ausência de duplicatas)

---

## 4. Referência Normativa

| Norma | Descrição | Relevância |
| --- | --- | --- |
|Decreto nº 5.992/2006 |Regulamenta a concessão de diárias no âmbito federal |Alta |
| Portaria MPOG nº 505/2009 |Tetos de diárias por categoria de servidor | Alta |
| Lei nº 9.748/1998 | Normas gerais sobre pagamentos a servidores | Média |
| COBIT 2019 — DSS06 |Gerenciar controles de processos de negócio | Média |
| COSO (2013) | Framework de controle interno — 5 componentes | Alta |

> **Nota:** Os valores de teto de diárias devem ser verificados na versão vigente da portaria no momento da auditoria, pois são atualizados periodicamente.

---

## 5. Matriz de Riscos

| # | Risco identificado |Probabilidade | Impacto | Nível de risco | Controle esperado |
| --- | --- | --- | --- | --- | --- |
| R01 | Pagamentos duplicados (mesmo CPF, valor e data) |Média | Alto | **Alto** |Chave única composta CPF + data + valor no sistema de lançamento | 
| R02 | Valores acima do teto legal (> R$ 1.100/dia) |Baixa | Alto | **Alto** |Validação automática de limite por cargo no momento da aprovação |
| R03 | Campos obrigatórios nulos (CPF, destino ou órgão) | Alta | Médio | **Alto** | Validação de campos obrigatórios no formulário de solicitação | 
| R04 | Viagens em fins de semana sem justificativa | Média | Médio | **Médio** |Obrigatoriedade de justificativa para datas atípicas no sistema |
| R05 | Concentração anormal em órgão ou servidor | Baixa | Médio | **Médio** |Monitoramento de frequência por CPF e alerta para valores > 3σ |
| R06 | Inconsistência de datas (retorno < saída) | Baixa | Baixo | **Baixo** |Validação de lógica temporal no cadastro da viagem |

### Critérios de classificação

**Probabilidade:** Alta = padrão histórico conhecido / Média = possível, sem evidência / Baixa = improvável

**Impacto:** Alto = risco financeiro ou legal relevante / Médio = falha de processo / Baixo = inconsistência pontual

---

## 6. Abordagem Metodológica — COSO

Os cinco componentes do COSO foram avaliados quanto à aplicabilidade neste projeto:

| Componente | Aplicação neste projeto | Status |  
| --- | --- | --- |  
| Ambiente de controle | Análise do contexto normativo e das políticas de pagamento | ✅ Aplicável |
| Avaliação de riscos | Matriz de riscos R01-R06 desta fase | ✅ Aplicável |
| Atividades de controle | Testes de auditoria nas Fases 3 e 4 | ✅ Aplicável |
| Informação e comunicação | Fora do escopo por limitação de acesso a sistemas internos | ⚠️ Parcial |
| Atividades de monitoramento | Dashboard de anomalias na Fase 4 | ✅ Aplicável |

---

## 7. Cronagrama da Fase 1

| Dia | Atividade | Entregável |
| --- | --- | --- |
| 1-2 | Definição de escopo e objetivos | Seções 2 e 3 deste documento |
| 3-4 | Pesquisa normativa | Seção 4 - Referência normativa |
| 5-6 | Elaboração da matriz de riscos | Seção 5 - Matriz de riscos |
| 7 | Revisão e versionamento | `docs/documento_planejamento_v1.md`v1.0 |

---

## 8. Aprovação

> **Revisando e aprovado em 15/05/20026.**
> Escopo confirmado. Riscos identificados e documentados.Autorizado o avanço para a Fase 2 - Coleta de Dados.
>
> Assinatura: Rafael Rachidi da Rocha

---

## Histórico de versões

| Versão | Data | Descrição |
| --- | --- | --- |
| 1.0 | 15/05/2026 | Versão inicial - planejamento completo da Fase 1 |