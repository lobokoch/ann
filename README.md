# Trabalho Final: Redes neurais e geociências

**FUNDAÇÃO UNIVERSIDADE REGIONAL DE BLUMENAU**  
**CENTRO DE CIÊNCIAS EXATAS E NATURAIS**  
**DEPARTAMENTO DE SISTEMAS E COMPUTAÇÃO**  
**Professor Daniel dos Santos**  
**Redes Neurais (Pós-graduação em Data Science)**  
**Aluno: Márcio Koch**  

## Objetivo do trabalho

O objetivo deste trabalho é utilizar o framework Pytorch para desenvolver diferentes 
arquiteturas de redes neurais e compará-las em problema de classificação de 
granulometria.
Abaixo segue o resultado.

Foram utilizadas três arquiteturas diferentes no trabalho. Abaixo elas são descritas.
**Notas:**
- a base de dados possui 30 features de entrada e 12 classes de saída;
- todas as arquiteturas utilizaram 70% dos dados para treino e 30% dos dados para testes;
- todas as arquiteturas utilizaram **CrossEntropyLoss** como critério de cálculo da **loss**.

### Arquitetura 1
Épocas: 100
Otimizador de gradiente: SGD (Stochastic Gradient Descent) - `SGD(model.parameters(), lr=0.01, momentum=0.9)`
Dropout: 20%
Configurações iniciais da rede: 
| Camada | Nós entrada | Nós saída |
|--|--|--|
| 1 | 30 | 50|
| 2 | 50 | 40|
| 3 | 40 | 30|
| 4 | 30 | 20|
| 5 | 20 | 12|

Configurações do forward:
- Dropout
- Função de ativação das 4 primeiras camadas: ReLu
- Função de ativação da 5 camada: Softmax

#### Resultados da arquitetura 1
- Algoritmo utilizado:
- Acurácia: 67,8 %
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura1)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura1)
-----------------------



