# 📐 Medidas DAX — Painel de Acompanhamento de TMR — PETRONECT

Este documento reúne as principais medidas DAX desenvolvidas no painel de monitoramento operacional de chamados, com foco em **SLA, TMR (Tempo Médio de Resolução)** e volume de atendimento.

As medidas foram construídas priorizando **clareza, performance e controle de contexto**, garantindo análises confiáveis para suporte à operação.

---

## 📑 Sumário

- #1--sla-e-controle-de-prazo
- #2--tempo-médio-de-atendimento-tma
- #3--volume-de-chamados
- #4--indicadores-operacionais

---

## 1️⃣ SLA e Controle de Prazo

### `SLA_PTB`
Calcula o percentual de chamados resolvidos dentro do prazo (SLA), com base no indicador de status do chamado.

```dax
SLA_PTB = 
VAR a =
    CALCULATE(
        DISTINCTCOUNT(COMPRAS[ID_Chamado]),
        'COMPRAS'[INDICADOR_SLA] = "DENTRO DO PRAZO"
    )

VAR b =
    CALCULATE(
        DISTINCTCOUNT(COMPRAS[ID_Chamado])
    )

RETURN DIVIDE(a, b)
```

🧠 **Lógica:**  
A medida calcula a razão entre os chamados dentro do prazo e o total de chamados. O uso de `DISTINCTCOUNT` garante que cada chamado seja contabilizado apenas uma vez, evitando duplicidade.

👉 Indicador crítico para monitoramento de **SLA operacional**.

---

## 2️⃣ Tempo Médio de Atendimento (TMA)

### `TMA_HRS`
Calcula o tempo médio de atendimento dos chamados no consolidado geral.

```dax
TMA_HRS = 
CALCULATE(
    AVERAGE(CONSOLIDADO[TMA_HRS])
)
```

🧠 **Lógica:**  
Utiliza `AVERAGE` para calcular o tempo médio em horas, considerando o contexto de filtro aplicado (período, tipo de chamado, área, etc.).

---

### `TMA_HRS_CADASTRO`
Calcula o tempo médio de atendimento exclusivamente para chamados da área de cadastro.

```dax
TMA_HRS_CADASTRO = 
CALCULATE(
    AVERAGE(CADASTRO[TMA_HRS])
)
```

🧠 **Lógica:**  
Mesma lógica do TMA geral, porém aplicado à base específica de cadastro, permitindo comparações entre áreas operacionais.

👉 Usado para identificar **diferenças de desempenho entre processos**.

---

## 3️⃣ Volume de Chamados

### `VOLUME_SAÍDAS`
Calcula o volume total de chamados resolvidos no período.

```dax
VOLUME_SAÍDAS = 
CALCULATE(
    DISTINCTCOUNT(CONSOLIDADO[INCIDENTE])
)
```

🧠 **Lógica:**  
Conta o número único de chamados (incidentes), garantindo consistência na contagem mesmo com múltiplos registros por chamado.

👉 Representa a **carga operacional total**.

---

### `VOLUME_SAÍDAS_CADASTRO`
Calcula o volume de chamados resolvidos especificamente pela área de cadastro.

```dax
VOLUME_SAÍDAS_CADASTRO = 
CALCULATE(
    DISTINCTCOUNT(CADASTRO[INCIDENTE])
)
```

🧠 **Lógica:**  
Permite análise segmentada da operação, diferenciando áreas e tipos de atendimento.

👉 Usado para identificar **distribuição de carga entre áreas**.

---

## 4️⃣ Indicadores Operacionais

As medidas apresentadas permitem compor indicadores-chave de performance operacional:

- **SLA (dentro do prazo)** → qualidade do atendimento  
- **TMA (Tempo Médio de Atendimento)** → eficiência  
- **Volume de Saídas** → carga operacional  
- **Segmentação por área (Cadastro x Compras)** → análise estrutural  

---

## 🧠 Padrões Técnicos Aplicados

As medidas seguem boas práticas de modelagem em DAX:

- **`VAR` + `RETURN`** → melhora performance e organização lógica;
- **`CALCULATE`** → controle explícito do contexto de filtro;
- **`DISTINCTCOUNT`** → evita duplicidade em métricas de chamados;
- **`AVERAGE`** → cálculo de indicadores de tempo;
- **`DIVIDE`** → tratamento seguro de divisão por zero.

---
