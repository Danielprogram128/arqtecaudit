# Regras de Auditoria Inteligente — v1

**Status:** Em construção  
**Versão:** v1  
**Última atualização:** 2026-04  

---

# 1. Objetivo

Definir regras de negócio auditáveis para o motor da plataforma, permitindo detecção contínua de inconsistências, riscos e desvios operacionais.

---

# 2. Estrutura padrão das regras

Cada regra deve conter:

- Objetivo
- Descrição lógica
- Dados necessários
- Condição de disparo
- Severidade
- Observações (quando necessário)

---

# 3. Severidade padrão

- Baixa
- Média
- Alta
- Crítica

---

# 4. Saída esperada

Cada regra deve gerar:

- alerta
- descrição clara
- impacto estimado
- sugestão de ação futura (fase 2)

---

# 5. REGRAS

---

## BLOCO 1 — REGRAS FINANCEIRAS

### Regra 001 — Pagamento duplicado exato  
Condição: Mesmo fornecedor + valor + data  
Severidade: Alta  

---

### Regra 002 — Pagamento duplicado por proximidade  
Condição: Mesmo fornecedor + valor + intervalo até X dias  
Severidade: Alta  

---

### Regra 003 — Pagamento acima da média histórica  
Condição: Valor > média + limite percentual  
Severidade: Alta  

---

### Regra 004 — Despesa sem descrição  
Condição: Descrição vazia ou genérica  
Severidade: Média  

---

### Regra 005 — Despesa sem centro de custo  
Condição: Centro de custo ausente  
Severidade: Média  

---

### Regra 006 — Pagamento fora do horário padrão  
Condição: Fora da janela operacional  
Severidade: Média  

---

### Regra 007 — Valor fracionado suspeito  
Condição: Múltiplos valores pequenos somando valor relevante  
Severidade: Alta  

---

### Regra 008 — Pagamento sem documento vinculado  
Condição: Ausência de documento  
Severidade: Alta  

---

## BLOCO 2 — FORNECEDORES

### Regra 009 — Aumento anormal por fornecedor  
Condição: Valor atual > média + limite  
Severidade: Alta  

---

### Regra 010 — Concentração excessiva  
Condição: Participação acima do limite  
Severidade: Média  

---

### Regra 011 — Fornecedor duplicado  
Condição: Alta similaridade de cadastro  
Severidade: Média  

---

### Regra 012 — Dados bancários iguais  
Condição: Mesma conta para fornecedores diferentes  
Severidade: Crítica  

---

### Regra 013 — Fornecedor sem histórico  
Condição: Fornecedor novo + valor alto  
Severidade: Média  

---

### Regra 014 — Pagamentos recorrentes incomuns  
Condição: Frequência fora do padrão  
Severidade: Média  

---

## BLOCO 3 — PROCESSOS

### Regra 015 — Pagamento sem aprovação  
Condição: Sem aprovação registrada  
Severidade: Crítica  

---

### Regra 016 — Aprovação posterior ao pagamento  
Condição: Aprovação > pagamento  
Severidade: Alta  

---

### Regra 017 — Falta de aprovador definido  
Condição: Processo sem responsável  
Severidade: Alta  

---

### Regra 018 — Processo sem rastreabilidade  
Condição: Falta de histórico  
Severidade: Alta  

---

### Regra 019 — Alteração após aprovação  
Condição: Dados alterados após aprovação  
Severidade: Alta  

---

### Regra 020 — Aprovações fora da hierarquia  
Condição: Fora da alçada  
Severidade: Alta  

---

## BLOCO 4 — COMPORTAMENTO E ANOMALIA

### Regra 021 — Variação por categoria  
Condição: Crescimento anormal  
Severidade: Média  

---

### Regra 022 — Desvio por usuário  
Condição: Fora do padrão histórico  
Severidade: Média  

---

### Regra 023 — Pico de atividade incomum  
Condição: Alta atividade em curto período  
Severidade: Média  

---

### Regra 024 — Operações repetitivas incomuns  
Condição: Padrão repetitivo  
Severidade: Média  

---

### Regra 025 — Movimentação fora do padrão geográfico  
Condição: Local fora do padrão  
Severidade: Média  

---

## BLOCO 5 — INTEGRIDADE DOS DADOS

### Regra 026 — Campo obrigatório ausente  
Condição: Campo vazio  
Severidade: Média  

---

### Regra 027 — Datas inconsistentes  
Condição: Ordem inválida  
Severidade: Alta  

---

### Regra 028 — Valor negativo indevido  
Condição: Valor inválido  
Severidade: Média  

---

### Regra 029 — Dados duplicados  
Condição: Registros iguais  
Severidade: Média  

---

### Regra 030 — Divergência entre sistemas  
Condição: Valores diferentes  
Severidade: Alta  

---

## BLOCO 6 — CONSISTÊNCIA AVANÇADA

### Regra 031 — Divergência entre valor e quantidade  
Condição: Incompatibilidade de cálculo  
Severidade: Alta  

---

### Regra 032 — Valor unitário fora do padrão  
Condição: Fora da média histórica  
Severidade: Alta  

---

### Regra 033 — Mudança brusca de item  
Condição: Item fora do padrão histórico  
Severidade: Média  

---

### Regra 034 — Reclassificação frequente  
Condição: Mudança constante de classificação  
Severidade: Média  

---

### Regra 035 — Diferença entre valor aprovado e pago  
Condição: Divergência entre valores  
Severidade: Alta  

---

## BLOCO 7 — CONTROLE OPERACIONAL

### Regra 036 — Execução sem solicitação  
Condição: Sem origem registrada  
Severidade: Alta  

---

### Regra 037 — Aprovação imediata suspeita  
Condição: Tempo muito baixo entre etapas  
Severidade: Média  

---

### Regra 038 — Autoaprovação  
Condição: Solicitante = aprovador  
Severidade: Crítica  

---

### Regra 039 — Aprovação em lote  
Condição: Muitas aprovações em sequência  
Severidade: Média  

---

### Regra 040 — Exclusão de registros críticos  
Condição: Exclusão relevante  
Severidade: Crítica  

---

## BLOCO 8 — TEMPORALIDADE

### Regra 041 — Concentração no fim do período  
Condição: Pico no fechamento  
Severidade: Média  

---

### Regra 042 — Pagamento antecipado incomum  
Condição: Antes do prazo  
Severidade: Média  

---

### Regra 043 — Atraso recorrente  
Condição: Atrasos frequentes  
Severidade: Média  

---

### Regra 044 — Frequência irregular  
Condição: Intervalos inconsistentes  
Severidade: Média  

---

### Regra 045 — Alteração frequente de datas  
Condição: Mudanças repetidas  
Severidade: Alta  

---

## BLOCO 9 — RISCO COMPORTAMENTAL

### Regra 046 — Aumento repentino por usuário  
Condição: Volume acima do padrão  
Severidade: Alta  

---

### Regra 047 — Atividade fora do horário habitual  
Condição: Fora do padrão do usuário  
Severidade: Média  

---

### Regra 048 — Sequência repetitiva manual  
Condição: Padrão repetido  
Severidade: Média  

---

### Regra 049 — Centralização de decisões  
Condição: Um único aprovador dominante  
Severidade: Alta  

---

### Regra 050 — Mudança global de comportamento  
Condição: Vários desvios simultâneos  
Severidade: Alta  

---

# 6. SCORE DE RISCO

## Peso por severidade

- Baixa = 5 pontos  
- Média = 10 pontos  
- Alta = 25 pontos  
- Crítica = 50 pontos  

---

## Fórmula base

Score = soma dos pesos das regras acionadas

---

## Fatores adicionais

### Recorrência

- 1 ocorrência → x1  
- 2–3 → x1.2  
- 4–6 → x1.5  
- 7+ → x2  

---

### Impacto financeiro

- Baixo → x1  
- Médio → x1.5  
- Alto → x2  
- Muito alto → x3  

---

## Classificação de risco

- 0–50 → Baixo 
- 51–150 → Moderado 
- 151–300 → Alto 
- 301+ → Crítico 

---

## Tipos de score

- Por empresa  
- Por usuário  
- Por fornecedor  
- Por processo  

---

# 7. DIRETRIZES DO MOTOR

- Todas as regras devem ser parametrizáveis  
- Devem permitir ativação/desativação  
- Devem gerar alertas estruturados  
- Devem evoluir com histórico  

---

# 8. EVOLUÇÃO FUTURA

- IA para ajuste automático  
- Score preditivo  
- Benchmark entre empresas  
- Prioridade inteligente de alertas  

---