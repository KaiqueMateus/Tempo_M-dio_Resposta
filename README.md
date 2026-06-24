# 📊 Painel de Acompanhamento de TMR - PETRONECT

>  Dashboard de Business Intelligence desenvolvido em **Power BI** para monitoramento e análise do **Tempo Médio de Resolução (TMR)** de chamados operacionais, integrando dados de **SAP, S/4HANA, ServiceNow e bases internas da Petronect**, com foco em controle de SLA, performance de atendimento e identificação de gargalos.

![License](https://img.shields.io/badge/License-MIT-blue)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-FFCA28)
![Power Query](https://img.shields.io/badge/Power_Query_M-1F6FEB)
![SAP](https://img.shields.io/badge/SAP-0FAAFF?logo=sap&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?logo=postgresql&logoColor=white)
![SAP HANA](https://img.shields.io/badge/SAP_HANA-0FAAFF?logo=sap&logoColor=white)
---

## 🖼️ Preview do Painel

<img width="1302" height="726" alt="Animação2" src="https://github.com/user-attachments/assets/bc63d8bc-42d0-4e81-89d8-c9615c494dc5" />

---

## 📌 Sumário

- [🎯 Visão Geral](#-visão-geral)
- [💼 Problema de Negócio](#-problema-de-negócio)
- [✅ Solução Desenvolvida](#-solução-desenvolvida)
- [🛠️ Stack Utilizada](#️-stack-utilizada)
- [🏗️ Arquitetura de Dados](#️-arquitetura-de-dados)
- [📈 KPIs Principais](#-kpis-principais)
- [💡 Insights e Impacto](#-insights-e-impacto)

---

## 🎯 Visão Geral

Este projeto foi desenvolvido como uma solução de Business Intelligence voltada ao monitoramento da performance operacional de atendimento de chamados na Petronect.

O painel consolida dados provenientes de múltiplas fontes **ServiceNow (gestão de chamados), SAP e S/4HANA (processos operacionais e transacionais)** — permitindo uma visão integrada do tempo de resolução, classificação de incidentes e desempenho por área.

A solução possibilita acompanhar o **Tempo Médio de Atendimento (TMA)** e identificar rapidamente gargalos no processo, apoiando times de operações, suporte e áreas de negócio na tomada de decisão baseada em dados.

---

## 💼 Problema de Negócio

Antes da implementação do painel, o acompanhamento dos chamados operacionais apresentava limitações:

- **Falta de visibilidade consolidada** do tempo de resolução (TMR) entre diferentes sistemas e áreas;
- Dificuldade em identificar **gargalos no fluxo de atendimento**;
- Ausência de controle eficiente sobre **indicadores de SLA**;
- Dependência de extração manual de dados em múltiplas fontes;
- Processos de análise reativos, sem suporte a decisões ágeis.

> **Pergunta de negócio:** Como monitorar, de forma integrada, o tempo de resolução de chamados e garantir controle eficiente de SLA e performance operacional?

---

## ✅ Solução Desenvolvida

Foi desenvolvido um dashboard executivo em Power BI, integrando dados de ServiceNow, SAP, S/4HANA e bases auxiliares em Excel, com foco no acompanhamento de indicadores operacionais de chamados.

A solução entrega:

- **Monitoramento do TMR / TMA em tempo real** por tipo de chamado;
- Segmentação por **Incidentes, Serviços e áreas operacionais**;
- Análise de volume de chamados ao longo do tempo;
- Identificação de **picos de demanda e gargalos operacionais**;
- Detalhamento individual de chamados (ID, categoria, SLA);
- Apoio à gestão operacional para melhoria contínua do atendimento.

---

## 🛠️ Stack Utilizada

| Categoria | Ferramentas |
|---|---|
| **Visualização** | Power BI |
| **ETL / Automação** | Alteryx |
| **Bases de Dados** | SAP, S/4HANA, ServiceNow, Excel |
| **Linguagens** | SQL, DAX |
| **Modelagem** | Star Schema |

---

## 🏗️ Arquitetura de Dados

```
SAP / S4HANA + ServiceNow Petronect + ServiceNow Petrobras + Excel
                ↓
       Alteryx (ETL e integração)
                ↓
     Modelagem (Star Schema)
                ↓
          Cálculo (DAX)
                ↓
     Dashboard Power BI
                ↓
          Usuário Final
```

---

## 📈 KPIs Principais

- **Volume de Chamados (Saída)**  
- **Tempo Médio de Atendimento (TMA em horas)**  
- **Tempo Médio de Resolução (TMR)**  
- **Distribuição por Tipo (Incidentes x Serviços)**  
- **Chamados por Área (Cadastro x Compras)**  
- **Volume mensal de atendimento**  
- **Detalhamento de chamados com SLA**  

---

## 💡 Insights e Impacto

A entrega do painel proporcionou ao cliente:

- ✅ Visão centralizada do tempo de resolução de chamados;
- ✅ Identificação rápida de gargalos no atendimento;
- ✅ Melhor controle de SLA e tempo de resposta;
- ✅ Aumento da eficiência operacional das equipes;
- ✅ Redução da dependência de análises manuais;
- ✅ Apoio direto à tomada de decisão em contextos críticos.

---

## 📚 Documentação Técnica

Para entender em profundidade as decisões técnicas, modelagem e fórmulas DAX:

- 📐 **01-medidas-dax.md** — 8 medidas DAX comentadas e organizadas por categoria
  
---
## 📌 Observação

> Os dados originais são confidenciais e pertencem a empresa PETRONECT. Este repositório contém **dados anonimizados e sintéticos** para fins de portfólio, mantendo a estrutura, a modelagem e a lógica analítica do projeto original.

---

## 👤 Autor

**Kaique Souza** — Analista de Dados e BI
📧 kaique8mateus@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/kaique-mateus-de-souza-0baa83238/) • [Portfólio](https://sites.google.com/view/portfolio-kaique-mateus/projetos) 
