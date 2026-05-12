# Projeto: [Saúde 4.0: Robótica Assistiva]

### 1. Identificação do Grupo
* **Instituição:** Fundação Salvador Arena
* **Curso:** Engenharia de Controle e Automação
* **Grupo:** Grupo 8
* **Integrantes:**
*   * Gustavo Florencio Lima Simião- RA: [061230041]
    * [Leonardo Rodolfo Bortoluci] - RA: [062220014]
    * [Julia Rodrigues Lima] - RA: [062220026]

---
### 🎥 Demonstração do Projeto
**[Assista ao Pitch e Demonstração da Solução ](https://youtu.be/9pO0D3D_aMs)**

### 2. Área Problema Selecionada
Selecione a trilha tecnológica do projeto (marque com um [x]):
* [x] **Saúde 4.0:** Robótica Assistiva (Controladores Inteligentes/Fuzzy)
* [ ] **Smart Grid:** Eficiência Energética e Descarbonização
* [ ] **Agtech:** Automação de Precisão e Visão Computacional
* [ ] **Logística Autônoma:** Coordenação de AGVs e Otimização de Rotas

---

### 3. Diagnóstico e Definição do Agente
Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

* **Contexto:**A Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro.
  
* **Problema:**  Doença de Parkinson é uma doença neurológica progressiva que afeta principalmente o controle dos movimentos. Ela ocorre devido à degeneração de neurônios produtores de dopamina no cérebro. 
Devido à natureza não linear, dinâmica e incerta dos sistemas biomecânicos humanos, abordagens baseadas em controle clássico apresentam limitações significativas.
  
* **Impacto:** redução significativa do tremor e na melhoria da qualidade de vida do paciente, permitindo maior autonomia em atividades do dia a dia como escrever, se alimentar e segurar objetos.

#### Modelagem PEAS (Agente Inteligente)
| Componente | Descrição |
| :--- | :--- |
| **Performance (P)** | Para que uma solução inteligente voltada a pacientes com Doença de Parkinson seja considerada bem-sucedida, o agente deve perseguir metas objetivas relacionadas à redução de sintomas, melhoria funcional e segurança clínica. A principal meta é reduzir significativamente a amplitude e a frequência do tremor sem prejudicar o movimento voluntário. Isso significa que o sistema deve ser capaz de identificar corretamente o tremor e aplicar compensação ativa apenas quando necessário. Um critério de sucesso mensurável seria, por exemplo, uma redução percentual consistente da amplitude do tremor medida por sensores inerciais, mantendo a fluidez do movimento intencional.
| **Ambiente (E)** | digital complementar, onde os dados coletados são processados, armazenados e analisados, podendo incluir sistemas embarcados e, em alguns casos, integração com plataformas de monitoramento clínico.
| **Atuadores (A)** | agente inteligente interage com o ambiente principalmente por meio de atuadores eletromecânicos, como motores ou servomotores acoplados a uma órtese ou exoesqueleto, que aplicam torque para compensar o tremor ou auxiliar o movimento.As decisões são executadas por um controlador embarcado (microcontrolador ou processador), que roda os algoritmos de IA e envia comandos aos motores. Esses comandos passam por um driver de potência, responsável por regular corrente e tensão com segurança.O sistema também utiliza feedback em malha fechada, com encoders e sensores de torque ou corrente, para garantir estabilidade e evitar sobrecompensação
| **Sensores (S) ** | Sensores Eletromiografia (EMG) de superfície - Permite diferenciar movimento voluntário de tremor,Unidade de Medição Inercial (IMU - acelerômetro + giroscópio) - Permite identificar padrão típico do tremor e medir sua intensidade, Giroscópio da IMU ou encoder no atuador - Necessário para aplicar compensação proporcional e estável e Sensor de torque ou corrente do motor - Garante controle seguro e evita sobrecompensação.

---

### 4. Arquitetura de Dados e IA
Definição das fontes de dados e da inteligência por trás da solução.

* **Origem dos Dados:** [Parkinson Disease Detection]([https://www.kaggle.com/datasets/fatemehmohammadinia/heart-attack-dataset-tarik-a-rashid](https://www.kaggle.com/datasets/debasisdotcom/parkinson-disease-detection)).
* **Lógica de IA:** Controladores Inteligentes/Fuzzy.
* **Justificativa:** Essa técnica — combinando Redes Neurais e controle inteligente — é ideal para esse problema porque a Doença de Parkinson envolve sinais motores altamente não lineares, variáveis e cheios de ruído, o que dificulta o uso de métodos tradicionais com parâmetros fixos. As Redes Neurais conseguem aprender padrões complexos dos sinais (como diferenciar tremor de movimento voluntário), enquanto técnicas como Lógica Fuzzy ou controle adaptativo permitem gerar respostas suaves e graduais, mais próximas do comportamento humano. Além disso, essas abordagens se adaptam ao paciente ao longo do tempo, acompanhando a progressão da doença, o que torna o sistema mais robusto, personalizado e eficaz em situações reais.

---

### 5. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:
1. **Extração:** Leitura automatizada do arquivo `Parkinsson disease.csv`via biblioteca Pandas.
2. **Transformação:** Limpeza de nulos, normalização e engenharia de atributos.
3. **Carga:** Disponibilização dos dados para o treinamento do modelo de IA.

---

### 6. Evidências Visuais e Desempenho
*Arquivos armazenados na pasta `/assets/images`.*

**Imagem 1: [Interface de Logs do Sistema de Monitoramento]**
[Demonstra a execução em tempo real do sistema, exibindo a identificação de biomarcadores (frequência de tremor e congelamento de marcha), o cálculo da probabilidade de intervenção e a sugestão clínica gerada pela IA.]
![Logs do Sistema](assets/images/Captura de tela 2026-05-11 094359.png).

**Imagem 2: [Modelagem da rede Neural]**
[Demonstra o desempenho do modelo de Deep Learning na classificação dos estados do paciente, apresentando a precisão da rede em distinguir entre movimentos normais, tremores e episódios de "freezing".]
![Rede Neural](assets/images/Captura de tela 2026-05-11 100757.png).

**Imagem 3: [Predição e Análise interpretativa]**
[O gráfico demonstra a modelagem dos conjuntos nebulosos (Fuzzy) para as variáveis de entrada e saída do sistema. Ele define os níveis de intensidade (como "baixo", "médio" e "alto") para o tremor detectado e o torque de compensação, permitindo que o algoritmo tome decisões graduais e precisas em vez de apenas "ligado/desligado".]
![Visualização da Lógica Fuzzy](assets/images/Captura de tela 2026-05-11 104201.png).

**Imagem 4: [Resposta do Gemini a Predição]**
[Demonstra a resposta do Gemini]
![Resposta Gemini](assets/images/Captura de tela 2026-05-11 104201.png).

---

### 7. Estrutura do Repositório
Organização simplificada para o Milestone 1:
* `/data`: Arquivos de dados originais (raw) e tratados (processed).
* `/notebooks`: Experimentos iniciais e análise exploratória.
* `/scripts`: Códigos Python (.py) contendo a lógica do agente e do ETL.
* `requirements.txt`: Lista de bibliotecas para rodar o projeto.
* `README.md`: Documentação atual do projeto.

---

### 8. Instruções para Execução
Para reproduzir o ambiente e testar o diagnóstico:
1. Clone este repositório `git clone [https://github.com/F10rencio/ECA8IA-SA-DE].
2. Instale as dependências:   
   ```bash
      pip install -r requirements.txt
   
### 🤖 9. Apêndice de IA

Relato sobre o suporte de ferramentas de Inteligência Artificial Generativa no desenvolvimento:

* **Ferramentas:** [Ex: Gemini, Google IA Studio].
* **Aplicação:** Apoio na estruturação do código, revisão textual, sugestão de métricas e organização do pipeline de ETL.
* **Validação:** Todos os resultados, métricas de desempenho e interpretações estatísticas foram conferidos e validados tecnicamente pelo grupo.

---
© 2026 - Projeto de Inteligência Artificial - Faculdade Engenheiro Salvador Arena  
