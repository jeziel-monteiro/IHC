# Classificação supervisionada aplicada a problemas de IHC

## Objetivo
<div align="justify">

&ensp;Este trabalho tem como objetivo central analisar e validar a aplicabilidade e a eficácia do fundamento da Comunicabilidade—conceito chave da Interação Humano-Computador (IHC) — por meio de técnicas de Classificação Supervisionada utilizando Machine Learning. A pesquisa utiliza uma base de dados sintética com atributos de esforço e tempo do usuário (Qtd_atividades, Qtd_erros, Tempo_gasto, etc.) para treinar algoritmos (como J48, OneR e IBk) na classificação da comunicabilidade em níveis Alta, Média ou Baixa, conforme regras de pontuação predefinidas. Os resultados experimentais, notavelmente a alta acurácia do algoritmo J48 (89.41%), demonstram que as regras de IHC definidas são logicamente consistentes e passíveis de serem "redescobertas" por modelos de aprendizado, validando quantitativamente os indicadores de usabilidade e sugerindo que a maior dificuldade dos modelos reside na inerente ambiguidade da classe "Média" de interação.

## Curso
- Engenharia de Software

## Integrantes 
- 22552563 - Arthur Djan Pinheiro Pontes
- 22550448 - Pâmilla Nunes Santos
- 22552725 - Heloyse Heloá Serrão Viana
- 22553221 - Jeziel Monteiro Pessoa
- 22551470 - Sérgio Augusto Simões da Silva

## Docente

- Andrey Antonio de Oliveira Rodrigues

## Arquitetura

![Arquitetura completa](https://i.postimg.cc/MHyJ5Mgn/Arquitetura-completa.png)

## 1 - Definição do problema

- [1.1 Contexto e motivação](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#11-contexto-e-motiva%C3%A7%C3%A3o)
- [1.2 Atributos](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#12-atributos)
- [1.3 Classe-alvo](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#13-classe-alvo)
- [1.4 Sistema](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#14-sistema)

## 2 - Regras usadas para gerar a classe-alvo
- [2.1 Tabela de pontuação por atributo](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#tabela-de-pontua%C3%A7%C3%A3o-por-atributo)

## 3 - Descrição da base sintética
- [3.1 Tabela de requisitos da base](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#31-tabela-de-requisitos-da-base)

## 4 - Descrição dos experimentos Weka
- [4.1 Ambiente e Conjunto de Dados](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#41-ambiente-e-conjunto-de-dados)
- [4.2 Algoritmos Selecionados](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#42-algoritmos-selecionados)

## 5 - Resultados
- [5.1 Tabela de Acurácia](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#51-tabela-de-acur%C3%A1cia)
- [5.2 Matriz de confusão](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#52-matriz-de-confus%C3%A3o)
- [5.3 Modelo de Árvore](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#53-modelo-de-%C3%A1rvore)
- [5.4 Comparação dos resultados](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#53-compara%C3%A7%C3%A3o-dos-resultados)
- [5.5 Validação das Regras Definidas](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#54-compara%C3%A7%C3%A3o-dos-resultados---valida%C3%A7%C3%A3o-das-regras-definidas)

## 6 - Análise crítica dos resultados em relação ao domínio de IHC
- [6.1 Análise crítica](https://github.com/jeziel-monteiro/IHC/blob/main/TP2%20-%20IHC/relatorio.md#an%C3%A1lise-cr%C3%ADtica)
