# Análise Financeira com Python — ClearBank

Projeto final do módulo de Python para Análise de Dados. Um notebook que lê, valida e analisa um histórico de transações bancárias de clientes fictícios da fintech **ClearBank**, gerando métricas financeiras mensais, identificando transações suspeitas e exportando o resultado em JSON.

## O que o projeto faz

1. Cria/lê o arquivo `transacoes.csv` com o histórico de transações.
2. Valida cada linha, descartando silenciosamente registros com dados inválidos (id, cliente_id, data, tipo ou valor incorretos), sem interromper o processamento.
3. Agrupa as transações válidas por mês, calculando quantidade, total de créditos, total de débitos, saldo, valor médio, maior e menor valor.
4. Identifica transações suspeitas (valor acima de R$ 10.000,00).
5. Exibe um relatório formatado no terminal.
6. Exporta o resultado da análise em `relatorio.json`.

## Como executar

1. Abra o notebook `desafio-final-jbg.ipynb` no [Google Colab](https://colab.research.google.com/).
2. O arquivo já esta rodado, mas pode tambem rodar todas as células em ordem, do início ao fim (no Colab: **Ambiente de execução → Executar tudo**).
3. Não é necessário instalar nenhuma biblioteca externa — o notebook usa apenas módulos nativos do Python (`csv`, `json`, `datetime`).
4. Requer Python 3.10 ou superior.

## O que o notebook gera como saída

- **No terminal:** um resumo da limpeza dos dados (total de linhas lidas, válidas e inválidas) e um relatório mensal formatado, com os totais em R$, seguido da lista de transações suspeitas.
- **Arquivo `relatorio.json`:** contém a data de geração, os totais de transações válidas/inválidas, o resumo mensal completo e a lista de transações suspeitas.

## Exemplo de saída no terminal

```
===== RESUMO DA LEITURA =====
Total de linhas lidas: 22
Linhas válidas: 15
Linhas inválidas: 7
Arquivo 'relatorio.json' salvo com sucesso.

Período analisado: 2026-01-05 até 2026-04-04
Total de transações válidas: 15
Total de transações inválidas: 7

===== RELATÓRIO MENSAL =====

Mês: 2026-01
  Transações: 3
  Total crédito: R$ 3.512,47
  Total débito:  R$ 111,70
  Saldo:         R$ 3.400,77
  Média:         R$ 1.208,06
  Maior valor:   R$ 3.512,47
  Menor valor:   R$ 42,80

===== RELATÓRIO MENSAL =====

Mês: 2026-02
  Transações: 5
  Total crédito: R$ 18.020,50
  Total débito:  R$ 665,34
  Saldo:         R$ 17.355,16
  Média:         R$ 3.737,17
  Maior valor:   R$ 15.230,90
  Menor valor:   R$ 54,60

===== RELATÓRIO MENSAL =====

Mês: 2026-03
  Transações: 6
  Total crédito: R$ 6.302,07
  Total débito:  R$ 12.374,72
  Saldo:         R$ -6.072,65
  Média:         R$ 3.112,80
  Maior valor:   R$ 12.045,80
  Menor valor:   R$ 33,90

===== RELATÓRIO MENSAL =====

Mês: 2026-04
  Transações: 1
  Total crédito: R$ 0,00
  Total débito:  R$ 94,30
  Saldo:         R$ -94,30
  Média:         R$ 94,30
  Maior valor:   R$ 94,30
  Menor valor:   R$ 94,30

===== TRANSAÇÕES SUSPEITAS =====
ID: 7 | Cliente: CLI001 | Data: 2026-02-14 | Valor: R$ 15.230,90
ID: 12 | Cliente: CLI003 | Data: 2026-03-11 | Valor: R$ 12.045,80
```

## Requisitos opcionais

Os requisitos opcionais (análise alternativa com `pandas` em `analise_pandas.py` e gráfico com `matplotlib` em `grafico.png`) **não foram implementados** neste projeto. O notebook cobre apenas os requisitos obrigatórios, usando somente módulos nativos do Python.

## Estrutura do repositório

```
clearbank-analise/
├── desafio-final.ipynb   # notebook com o código e as saídas salvas
└── README.md              # este arquivo
```
