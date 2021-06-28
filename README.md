# (WIP) Trabalho Final: Redes neurais e geociências

**FUNDAÇÃO UNIVERSIDADE REGIONAL DE BLUMENAU**  
**CENTRO DE CIÊNCIAS EXATAS E NATURAIS**  
**DEPARTAMENTO DE SISTEMAS E COMPUTAÇÃO**  
**Professor: Daniel dos Santos**  
**Disciplina: Redes Neurais (Pós-graduação em Data Science)**  
**Aluno: Márcio Koch**  

## Objetivo do trabalho

O objetivo deste trabalho é utilizar o framework Pytorch para desenvolver diferentes 
arquiteturas de redes neurais e compará-las em problema de classificação de 
granulometria.
Abaixo segue o resultado.

Foram criadas 4 arquiteturas de redes neurais diferentes no trabalho. Abaixo elas estão descritas.  
**Notas:**
- o Dataset para treinamento possui **30 features** de **entrada** e **12 classes** de **saída**;
- O Dataset de entrada, um arquivo CSV (arquivo lithology.csv disponibilizado pelo professor Daniel) possui na primeira linha os títulos das colunas e possui **1.170.511** linhas de dados para treinamento;
- todas as arquiteturas utilizaram **70%** dos dados para treino e **30%** dos dados para testes;
- todas as arquiteturas utilizaram **CrossEntropyLoss** como critério de cálculo da **loss**.

### Arquitetura 1
- Épocas: **100**
- Otimizador de gradiente: **SGD** - `SGD(model.parameters(), lr=0.01, momentum=0.9)`  
- Dropout: **20%**

Configurações iniciais da rede: 
| Camada | Nós entrada | Nós saída | Dropout | Função de ativação |  
|--|--|--|--|--|
| 1 | **30** | 50| Sim | ReLu |
| 2 | 50 | 40| Sim | ReLu |
| 3 | 40 | 30| Sim | ReLu |
| 4 | 30 | 20| Sim | ReLu |
| 5 | 20 | **12**| Não | Softmax |

#### Resultados da arquitetura
- Acurácia: **14,4 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura1)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura1)
-----------------------

### Arquitetura 2
- Épocas: **100**
- Otimizador de gradiente:  **Adam** - `Adam(model.parameters(), lr=0.003)`  
- Dropout: **20%**

Configurações iniciais da rede:   
| Camada | Nós entrada | Nós saída |  Dropout | Função de ativação |  
|--|--|--|--|--|
| 1 | **30** | 200| Sim | ReLu |
| 2 | 200 | 100| Sim | ReLu |
| 3 | 100 | 80| Sim | ReLu |
| 4 | 80 | **12**| Não | Softmax |

#### Resultados da arquitetura
- Acurácia: **61,6 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura2)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura2)
-----------------------

### Arquitetura 3
- Épocas: **50**
- Otimizador de gradiente: **SGD** - `SGD(model.parameters(), lr=0.01, momentum=0.9)`  

Configurações iniciais da rede:   
| Camada | Nós entrada | Nós saída | Alg. ini. pesos| Função de ativação |  
|--|--|--|--|--|
| 1 | **30** | 1024| kaiming | ReLu |
| 2 | 1024| 512| kaiming | ReLu |
| 3 | 512| 256| kaiming | ReLu |
| 4 | 256 | 256| kaiming | ReLu |
| 5 | 256 | 256| kaiming | ReLu |
| 6 | 256 | 256| kaiming | ReLu |
| 7 | 256 | **12**| xavier | Softmax |

#### Resultados da arquitetura
- Acurácia: **0,01 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura3)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura3)
-----------------------

### Arquitetura 4
- Épocas: **300**
- Otimizador de gradiente: **SGD** - `SGD(model.parameters(), lr=0.01, momentum=0.9)`  

Configurações iniciais da rede:   
| Camada | Nós entrada | Nós saída | Função de ativação |  
|--|--|--|--|
| 1 | **30** | 50 |  hyperbolic tangent |
| 2 | 50 | 40 |  hyperbolic tangent |
| 3 | 40 | 30 |  hyperbolic tangent |
| 4 | 30 | 20 |  hyperbolic tangent |
| 5 | 20 | **12** |  n/a |

#### Resultados da arquitetura
- Acurácia: **61,5 %**
- [Arquivo de código fonte da implementação](https://github.com/lobokoch/ann/tree/main/arquitetura4)
- [Arquivo de resultado hidden.csv](https://github.com/lobokoch/ann/tree/main/arquitetura4)
-----------------------


