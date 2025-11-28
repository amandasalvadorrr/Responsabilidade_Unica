# Refatoração Aplicando o Princípio da Responsabilidade Única (SRP)

Este repositório contém uma atividade de refatoração cujo objetivo é aplicar o **Princípio da Responsabilidade Única (SRP)**, um dos pilares do SOLID. O SRP afirma que uma classe deve possuir **apenas uma responsabilidade**, ou seja, apenas um motivo para mudar.

## Problema Identificado

O código original apresenta a classe `Funcionario`, que viola completamente o SRP ao acumular três responsabilidades distintas:

### 1. Gestão de Dados  
Responsável por salvar e carregar informações do funcionário, algo que deveria pertencer a uma classe de persistência.

### 2. Regra de Negócio  
Inclui o cálculo do salário, que deveria estar isolado em uma classe voltada exclusivamente à lógica de negócio.

### 3. Apresentação / Relatório  
Gera relatórios e impressões, responsabilidade que deveria estar em um componente dedicado à formatação e exibição de informações.

Reunir essas três funções em uma única classe torna o código difícil de manter, testar e evoluir. Qualquer alteração em uma dessas áreas afeta as outras, causando múltiplos motivos de mudança e violando diretamente o SRP.

## Objetivo da Refatoração

A refatoração busca separar cada responsabilidade em sua própria classe, tornando o código:

- Mais modular  
- Mais fácil de manter  
- Mais simples de testar  
- Aderente aos princípios SOLID  

A solução final distribui as responsabilidades da seguinte forma:

- **Classe de Modelo (`Funcionario`)**: apenas armazena dados.  
- **Serviço de Cálculo (`CalculadoraDeSalario`)**: responsável pelas regras de negócio.  
- **Repositório (`RepositorioDeFuncionario`)**: lida com armazenamento e recuperação de dados.  
- **Gerador de Relatório (`GeradorDeRelatorio`)**: cuida da apresentação das informações.

Com essa divisão, o código preserva o SRP e se torna mais organizado e sustentável.

