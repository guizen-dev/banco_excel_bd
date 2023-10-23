# Banco de dados reestruturado no Excel
Projeto feito no curso de *Programação de Banco de Bados* no senai. O objetivo era reestruturar a tabela default de mode que seguisse até a 3ª normalização de banco de dados (3FN), para que o projeto ficasse mais compeensivel e replicável.

## Tabela Clientes Original (sem normalização)
| COD | NOME DO CLIENTE     | CPF | TELEFONES2 | CIDADE     | UF | BANCO                   | AGENCIA          | CONTA     | SALDO  |
|-----|----------------------|-----|------------|------------|---|-------------------------|------------------|----------|--------|
| 1   | JOSE DA SILVA       | 111 | 89387483   | BELO HTE   | MG| 001 - Banco do Brasil  | 0219 - Praça    | 9384-1   | 10,00  |
|     |                    |     | 89748950   |            |   | 033 - Santander        | 0343 - Shopping | 9873-7   | 40,00  |
|     |                    |     |            |            |   | 104 - Caixa            | 0034 - Matriz   | 0349-8   | 100,00 |
| 2   | JOAO GAVIAO         | 222 | 89865869   | CONTAGEM   | MG| 001 - Banco do Brasil  | 0219 - Praça    | 9344-2   | 32,00  |
| 3   | MARIA DAS TRANCAS   | 343 | 89487494   | BELO HTE   | MG| 001 - Banco do Brasil  | 0001 - Matriz   | 9098-0   | 13,00  |
|     |                    |     |            |            |   | 104 - Caixa            | 0394 - Engenho  | 0837-5   | 34,00  |
| 4   | PEDRO LUIZ          | 948 | 99809495   | SÃO PAULO  | SP| 104 - Caixa            | 0394 - Engenho  | 9489-8   | 99,00  |


## Banco de dados normalizado e estruturado

#### Tabela CLIENTES

| COD | NOME DO CLIENTE     | CPF | COD_CIDADE |
|-----|----------------------|-----|------------|
| 1   | JOSE DA SILVA       | 111 | 1          |
| 2   | JOAO GAVIAO         | 222 | 2          |
| 3   | MARIA DAS TRANCAS   | 343 | 1          |
| 4   | PEDRO LUIZ          | 948 | 3          |

#### Tabela CLIENTE_BANCO

| COD_CLIENTE | COD_AGENCIA | CONTA    | SALDO  |
|------------|------------|---------|--------|
| 1          | 219        | 9384-1  | 10.00  |
| 1          | 343        | 9873-7  | 40.00  |
| 1          | 34         | 0349-8  | 100.00 |
| 2          | 219        | 9344-2  | 32.00  |
| 3          | 1          | 9098-0  | 13.00  |
| 4          | 394        | 0837-5  | 34.00  |
| 4          | 394        | 9489-8  | 99.00  |

#### Tabela TELEFONES CLIENTE

| COD | COD_CLIENTE | TELEFONE |
|-----|------------|----------|
| 1   | 1          | 89387483 |
| 2   | 1          | 89748950 |
| 3   | 2          | 89865869 |
| 4   | 2          | 89487494 |
| 5   | 3          | 99809495 |
| 6   | 3          | 99849593 |

#### Tabela BANCO

| COD | NOME            |
|-----|-----------------|
| 1   | Banco do Brasil |
| 33  | Santander       |
| 104 | Caixa           |

#### Tabela AGENCIA_BANCO

| COD   | COD_LOCAL_AGENCIA | COD_BANCO |
|-------|-------------------|-----------|
| 219   | 1                 | 1         |
| 343   | 2                 | 33        |
| 34    | 3                 | 104       |
| 1     | 3                 | 1         |
| 394   | 4                 | 104       |

#### Tabela LOCAL_AGENCIA

| COD | NOME_LOCAL |
|-----|------------|
| 1   | Praça      |
| 2   | Shopping   |
| 3   | Matriz     |
| 4   | Engenho    |

#### Tabela CIDADE

| COD | CIDADE          | COD_UF |
|-----|-----------------|--------|
| 1   | BELO HORIZONTE  | 1      |
| 2   | CONTAGEM        | 1      |
| 3   | SAO PAULO       | 2      |

#### Tabela UNIDADE FEDERATIVA

| COD | NOME |
|-----|------|
| 1   | MG   |
| 2   | SP   |

## Excel
![Captura de tela 2023-10-23 155119](https://github.com/guizen-dev/banco_excel_bd/assets/94479811/64c39f5f-579c-430f-bc77-bd6c637183f9)

