# Projeto de Suporte de Parede Articulado para Bicicletas

<p align="center">
  <img src="https://img.shields.io/badge/Categoria-Projeto%20Académico-blue" alt="Categoria: Projeto Académico">
  <img src="https://img.shields.io/badge/Software-SolidEdge-0072C6?logo=siemens" alt="Software: SolidEdge">
</p>

> [Projeto Académico] Projeto de um suporte de parede articulado para duas bicicletas (50kg ), incluindo dimensionamento estrutural, análise de tensões (SolidEdge), estudo de materiais (Aço ST37 vs. Alumínio AW6063) e processos de fabrico.

---

## Índice

- Introdução, Objetivos e Enquadramento
- Evolução do Conceito
- Dimensionamento e Seleção dos Componentes
  - Análise da Estrutura (Passagem de 3D para 2D)
  - Seleção dos Materiais e Parâmetros Teóricos
  - Barra Central e Braço Lateral: Reações e Diagramas de Esforços Internos
  - Dimensionamento dos Pinos de Articulação, Pinos de Limitação e Chumaceiras
  - Identificação e Caracterização de Componentes
- Modelação 3D e Simulações
  - Análise de Tensões na Modelação 3D
  - Comparação entre Resultados da Simulação e Cálculos Analíticos
- Construção do Equipamento e Tecnologias de Fabrico
- Conclusões e Melhorias Futuras
- Documentação do Projeto
- Licença

---

### 1. Introdução, Objetivos e Enquadramento

Este repositório documenta o desenvolvimento do **Projeto Temático em Conceção e Produção Assistida por Computador**, realizado no âmbito da UC de Projeto Temático de Conceção e Produção Assistida por Computador, da Licenciatura em Eletrónica e Mecânica Industrial da ESTGA – Escola Superior de Tecnologia e Gestão de Águeda, da Universidade de Aveiro. O projeto teve como foco a conceção de um suporte de parede articulado para armazenamento eficiente de bicicletas.

A proposta inicial previa a acomodação de duas a três bicicletas, com uma carga total de 75 kg (25 kg por unidade). No entanto, após análise técnica, optou-se por uma solução otimizada para **duas bicicletas, com capacidade total de 50 kg**. Esta decisão baseou-se em critérios como a eficiência na utilização do espaço, a segurança estrutural, a viabilidade construtiva e a simplicidade de fabrico. Concluiu-se que a adaptação para três bicicletas implicaria apenas alterações nas secções estruturais, sem impacto significativo no conceito geral.

O desenvolvimento do suporte teve como objetivo criar uma estrutura modular, segura, funcional e de fácil instalação, assegurando desempenho mecânico, estética e durabilidade. Ao longo do projeto, foram aplicados conhecimentos técnicos adquiridos nas unidades curriculares associadas, permitindo realizar o dimensionamento estrutural mecânico, o cálculo de cargas e esforços, as simulações computacionais (recorrendo aos softwares SolidEdge e MDSolids), a modelação 3D do sistema, a seleção criteriosa de materiais com base em propriedades mecânicas e disponibilidade no mercado, e a definição dos processos tecnológicos de fabrico mais adequados.

### 2. Evolução do Conceito

O processo de conceção passou por várias iterações, sempre com base em critérios de viabilidade prática, simplicidade construtiva e funcionalidade:

-   **Ideia Inicial (3 Colunas Ocas de Aço):** Um sistema ambicioso com mecanismos mecânicos internos para suportar até três bicicletas. Rapidamente revelou-se impraticável devido ao espaço ocupado e à dificuldade de acesso individual às bicicletas. Esta abordagem foi abandonada.
-   **Conceito Alternativo (Sistema de Polias e Alavancas):** Semelhante a um estendal de roupa, fixo à parede. Descartado por questões de complexidade na manutenção, falta de conhecimento técnico específico e fragilidade estrutural, após discussões com os professores orientadores.
-   **Solução Final (Braços Articulados):** A proposta final e adotada consiste num suporte composto por dois braços laterais articulados e uma barra central de apoio, criando um sistema mecânico mais compacto e fácil de utilizar. Esta solução permite o arrumo de duas bicicletas de forma independente.

### 3. Dimensionamento e Seleção dos Componentes

Esta fase detalhou a análise estrutural, desde a simplificação do modelo 3D para 2D até aos diagramas de esforços internos, passando pelo cálculo de reações nos apoios, dimensionamento dos vários elementos e seleção de materiais e perfis. Todos os cálculos foram realizados com um **fator de segurança (n) de 1,5**.

#### 3.1. Análise da Estrutura (Passagem de 3D para 2D)

Para simplificar os cálculos, a estrutura 3D foi analisada em 2D, considerando os piores cenários de carregamento. As forças e momentos foram calculados para determinar as tensões e deformações nos componentes.

#### 3.2. Seleção dos Materiais e Parâmetros Teóricos

Foram comparados o Aço ST37 e o Alumínio AW 6063 para os perfis estruturais, com base nas suas propriedades mecânicas e disponibilidade no mercado.

| Material | Tensão de Cedência (R_p0.2) | Tensão Admissível (σ_adm = R_p0.2 / n) |
| :--- | :---: | :---: |
| **Aço ST37** | 235 MPa | 156,67 MPa |
| **Alumínio AW 6063** | 170 MPa | 113,33 MPa |

-   **Barra Central e Braço Lateral:** Optou-se pelo **Alumínio AW 6063** (perfil oco circular) devido à sua estética e resistência à corrosão. Embora a sua tensão de cedência seja inferior à do aço, o dimensionamento foi ajustado para garantir a resistência necessária, resultando num diâmetro ligeiramente maior.
-   **Suporte da Roda e Chapas:** Para estes componentes, foi selecionado o **Aço ST37**. A sua maior tensão de cedência permitiu reduzir as dimensões das peças, mantendo a robustez e segurança necessárias.

#### 3.3. Barra Central e Braço Lateral: Reações e Diagramas de Esforços Internos

Foram realizados cálculos analíticos detalhados para determinar as reações nos apoios e os diagramas de esforços internos (normais, cortantes e momentos fletores) para os componentes críticos. A imagem abaixo ilustra um dos Diagramas de Corpo Livre (DCL) e os cálculos de momento para determinar as forças em jogo, considerando uma força de 550N aplicada.

**Cálculo do Momento Fletor:**

Para determinar a força `X` que equilibra os momentos, utilizou-se a equação de equilíbrio de momentos:

$M_1 = M_2 \\ 550 N \times 0.24982 m = X \times 0.50997 m \\ X = \frac{550 N \times 0.24982 m}{0.50997 m} \\ X = 269.43 N$

Este cálculo é fundamental para o dimensionamento da barra central e dos braços laterais, garantindo que suportam as cargas sem exceder as tensões admissíveis.

#### 3.4. Dimensionamento dos Pinos de Articulação, Pinos de Limitação e Chumaceiras

-   **Pinos de Articulação (Pino A, B, C):** Calculados para resistir ao corte e esmagamento. Embora os cálculos iniciais pudessem indicar diâmetros menores, foram sobredimensionados para **8 mm** para corresponder aos furos de fixação dos cilindros de gás e garantir maior robustez e padronização. O Pino C, por exemplo, foi inicialmente calculado, mas optou-se por uma ligação soldada para maior rigidez.
-   **Pinos de Limitação de Movimento:** Dimensionados para suportar as forças de impacto e garantir que o braço lateral não exceda os ângulos de operação seguros (ex: 30°+27°=57° e 180°-57°=123°).
-   **Chumaceiras (PAP 2215 P10):** Selecionadas para permitir a rotação suave do suporte da roda sobre a barra central, minimizando o atrito e o desgaste.
-   **Cilindros de Gás (Amortecedores):** Especificados com uma força de **550N** e um curso de 900mm (máx.) a 500mm (mín.) para auxiliar no movimento de subida e descida da estrutura, compensando parte do peso das bicicletas.

#### 3.5. Identificação e Caracterização de Componentes

Foram detalhados os componentes não normalizados, como o suporte da roda, a chapa de suporte do braço lateral e a chumaceira, com as suas cotas e características específicas. Por exemplo, o suporte da roda foi fabricado em Aço ST37 para permitir dimensões reduzidas mantendo a resistência.

### 4. Modelação 3D e Simulações

Todo o conjunto foi modelado em **SolidEdge**, permitindo a criação de desenhos de detalhe, vistas explodidas e, crucialmente, a validação do projeto através de simulação por elementos finitos (FEA).

#### 4.1. Análise de Tensões na Modelação 3D

-   A simulação por elementos finitos no SolidEdge permitiu visualizar a distribuição de tensões nos componentes sob carga máxima. Esta análise confirmou que as tensões máximas calculadas nos pontos críticos eram inferiores à tensão admissível dos materiais escolhidos, garantindo a segurança estrutural do suporte.

#### 4.2. Comparação entre Resultados da Simulação e Cálculos Analíticos

-   Os resultados obtidos através da simulação computacional foram comparados com os cálculos analíticos realizados manualmente. Esta comparação validou a precisão do dimensionamento teórico e a fiabilidade do modelo 3D, reforçando a confiança no design final.

### 5. Construção do Equipamento e Tecnologias de Fabrico

Foram definidos os processos de fabrico mais adequados para cada componente, visando a otimização da produção e a qualidade final, embora nunca tenha sido feito na realidade porque a montagem não contemplava o enununciado:

-   **Corte:** Quinagem e corte a laser para as chapas metálicas, garantindo precisão e acabamento.
-   **Maquinagem:** Torneamento e fresagem para os pinos, chumaceiras e outros componentes com geometrias complexas.
-   **Soldadura:** Utilizada para unir componentes específicos, como na articulação do pino C, onde uma ligação soldada foi preferida para maior rigidez e durabilidade em detrimento de uma articulação mecânica.
-   **Montagem:** Definição da sequência de montagem de todos os componentes, incluindo a instalação dos cilindros de gás e o ajuste das chumaceiras.

### 6. Conclusões e Melhorias Futuras

O projeto foi concluído com sucesso, resultando num design robusto, funcional e fabricável para o suporte de bicicletas. As principais aprendizagens centraram-se na aplicação prática de conceitos de Resistência de Materiais, na importância da seleção criteriosa de materiais e na integração entre o cálculo analítico e a validação por simulação computacional.

### 7. Licença

Este projeto está licenciado sob a **MIT License**. Veja o ficheiro `LICENSE` para mais detalhes.

